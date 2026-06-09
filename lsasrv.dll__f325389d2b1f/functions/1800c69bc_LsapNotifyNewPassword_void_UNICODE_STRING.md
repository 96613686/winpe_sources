# LsapNotifyNewPassword(void *,_UNICODE_STRING *)

- ea: `0x1800c69bc`
- end: `0x1800c6c27`
- name: `?LsapNotifyNewPassword@@YAXPEAXPEAU_UNICODE_STRING@@@Z`
- size: `619`
- prototype: `void __fastcall(void *, struct _UNICODE_STRING *)`
- caller_count: `4`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180063030`
- `0x1800c6dd0`
- `0x1800c6de0`
- `0x180125c28`

## callees

- `0x180009330`
- `0x180011278`
- `0x1800ada18`
- `0x1800b86d0`
- `0x1800bd6e0`
- `0x1800c69bc`
- `0x1800c6c30`
- `0x18014a6b0`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6b09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6b40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6b97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6b09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6b40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6b97`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800c6bc5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800c6bc5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c6adc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c6adc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c6af9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c6af9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c6bd5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c6bd5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800c6b6b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800c6b6b`

## pseudocode

```c
void __fastcall LsapNotifyNewPassword(void *a1, struct _UNICODE_STRING *a2, __int64 a3, __int64 a4)
{
  void **p_TokenHandle; // rbx
  __int64 v5; // rsi
  __int64 v6; // rdi
  unsigned __int64 v9; // rcx
  __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  void *v12; // rsp
  void *v13; // rsp
  _DWORD *v14; // rax
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  __int64 v17; // rdx
  void **v18; // rax
  __int64 v19; // [rsp+0h] [rbp-20h] BYREF
  void *TokenHandle; // [rsp+20h] [rbp+0h] BYREF
  __int64 v21; // [rsp+28h] [rbp+8h] BYREF

  p_TokenHandle = 0;
  v5 = (unsigned int)a2->Length + 2;
  TokenHandle = 0;
  v6 = (unsigned int)v5;
  if ( (unsigned int)v5 <= (unsigned __int64)g_ulMaxStackAllocSize )
  {
    v9 = (unsigned int)v5 + g_ulAdditionalProbeSize + 8;
    if ( v9 >= (unsigned int)v5 )
    {
      if ( (unsigned int)VerifyStackAvailable(v9, a2, a3, a4) )
      {
        v10 = v5 + 23;
        if ( v5 + 23 <= (unsigned __int64)(v5 + 8) )
          v10 = 0xFFFFFFFFFFFFFF0LL;
        v11 = v10 & 0xFFFFFFFFFFFFFFF0uLL;
        v12 = alloca(v11);
        v13 = alloca(v11);
        p_TokenHandle = &TokenHandle;
        if ( &v19 != (__int64 *)-32LL )
        {
          LODWORD(TokenHandle) = 1801679955;
          p_TokenHandle = (void **)&v21;
          if ( &v21 )
            goto LABEL_15;
        }
      }
    }
  }
  if ( v5 + 8 < (unsigned __int64)(unsigned int)v5 )
  {
LABEL_11:
    if ( !p_TokenHandle )
      goto LABEL_12;
LABEL_15:
    memcpy_0(p_TokenHandle, a2->Buffer, a2->Length);
    *((_WORD *)p_TokenHandle + ((unsigned __int64)(unsigned int)v5 >> 1) - 1) = 0;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xCu, 0, &TokenHandle) )
    {
      if ( !RevertToSelf() )
      {
        if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
        {
          goto LABEL_26;
        }
        LastError = GetLastError();
        v17 = 13;
LABEL_20:
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids, LastError);
        goto LABEL_26;
      }
    }
    else if ( GetLastError() != 1008 )
    {
      if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      {
        goto LABEL_26;
      }
      LastError = GetLastError();
      v17 = 12;
      goto LABEL_20;
    }
    LsapUpdateCredentialStuffers(a1, (unsigned __int16 *)p_TokenHandle, (unsigned int)v5 >> 1);
    goto LABEL_26;
  }
  v14 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
  p_TokenHandle = (void **)v14;
  if ( v14 )
  {
    *v14 = 1885431112;
    p_TokenHandle = (void **)(v14 + 2);
    goto LABEL_11;
  }
LABEL_12:
  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids);
LABEL_26:
  if ( TokenHandle )
  {
    SetThreadToken(0, TokenHandle);
    CloseHandle(TokenHandle);
  }
  if ( p_TokenHandle )
  {
    v18 = p_TokenHandle;
    do
    {
      *(_BYTE *)v18 = 0;
      v18 = (void **)((char *)v18 + 1);
      --v6;
    }
    while ( v6 );
    if ( *((_DWORD *)p_TokenHandle - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
  }
}

```

## disassembly

```asm
0x1800c69bc  push    rbp
0x1800c69be  push    rbx
0x1800c69bf  push    rsi
0x1800c69c0  push    rdi
0x1800c69c1  push    r14
0x1800c69c3  push    r15
0x1800c69c5  sub     rsp, 48h
0x1800c69c9  lea     rbp, [rsp+20h]
0x1800c69ce  mov     rax, cs:__security_cookie
0x1800c69d5  xor     rax, rbp
0x1800c69d8  mov     [rbp+50h+var_40], rax
0x1800c69dc  movzx   esi, word ptr [rdx]
0x1800c69df  xor     ebx, ebx
0x1800c69e1  add     esi, 2
0x1800c69e4  mov     [rbp+50h+TokenHandle], 0
0x1800c69ec  mov     edi, esi
0x1800c69ee  mov     r14, rdx
0x1800c69f1  cmp     rdi, cs:g_ulMaxStackAllocSize
0x1800c69f8  mov     r15, rcx
0x1800c69fb  ja      short loc_1800C6A55
0x1800c69fd  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800c6a04  add     rcx, 8
0x1800c6a08  add     rcx, rdi
0x1800c6a0b  cmp     rcx, rdi
0x1800c6a0e  jb      short loc_1800C6A55
0x1800c6a10  call    VerifyStackAvailable
0x1800c6a15  test    eax, eax
0x1800c6a17  jz      short loc_1800C6A55
0x1800c6a19  lea     rax, [rsi+8]
0x1800c6a1d  lea     rcx, [rax+0Fh]
0x1800c6a21  cmp     rcx, rax
0x1800c6a24  ja      short loc_1800C6A30
0x1800c6a26  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800c6a30  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800c6a34  mov     rax, rcx
0x1800c6a37  call    _alloca_probe
0x1800c6a3c  sub     rsp, rcx
0x1800c6a3f  lea     rbx, [rsp+70h+TokenHandle]
0x1800c6a44  test    rbx, rbx
0x1800c6a47  jz      short loc_1800C6A55
0x1800c6a49  mov     dword ptr [rbx], 6B637453h
0x1800c6a4f  add     rbx, 8
0x1800c6a53  jnz     short loc_1800C6ABF
0x1800c6a55  lea     rcx, [rsi+8]
0x1800c6a59  cmp     rcx, rdi
0x1800c6a5c  jb      short loc_1800C6A7C
0x1800c6a5e  mov     rax, cs:g_pfnAllocate
0x1800c6a65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6a6a  mov     rbx, rax
0x1800c6a6d  test    rax, rax
0x1800c6a70  jz      short loc_1800C6A81
0x1800c6a72  mov     dword ptr [rax], 70616548h
0x1800c6a78  add     rbx, 8
0x1800c6a7c  test    rbx, rbx
0x1800c6a7f  jnz     short loc_1800C6ABF
0x1800c6a81  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c6a88  lea     rax, WPP_GLOBAL_Control
0x1800c6a8f  cmp     rcx, rax
0x1800c6a92  jz      loc_1800C6BBA
0x1800c6a98  test    dword ptr [rcx+1Ch], 200h
0x1800c6a9f  jz      loc_1800C6BBA
0x1800c6aa5  mov     rcx, [rcx+10h]
0x1800c6aa9  lea     r8, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids
0x1800c6ab0  mov     edx, 0Bh
0x1800c6ab5  call    WPP_SF_
0x1800c6aba  jmp     loc_1800C6BBA
0x1800c6abf  movzx   r8d, word ptr [r14]; Size
0x1800c6ac3  mov     rcx, rbx; void *
0x1800c6ac6  mov     rdx, [r14+8]; Src
0x1800c6aca  call    memcpy_0
0x1800c6acf  xor     eax, eax
0x1800c6ad1  mov     rcx, rdi
0x1800c6ad4  shr     rcx, 1
0x1800c6ad7  mov     [rbx+rcx*2-2], ax
0x1800c6adc  call    cs:__imp_GetCurrentThread
0x1800c6ae3  nop     dword ptr [rax+rax+00h]
0x1800c6ae8  xor     r8d, r8d; OpenAsSelf
0x1800c6aeb  lea     r9, [rbp+50h+TokenHandle]; TokenHandle
0x1800c6aef  mov     rcx, rax; ThreadHandle
0x1800c6af2  lea     r14d, [r8+0Ch]
0x1800c6af6  mov     edx, r14d; DesiredAccess
0x1800c6af9  call    cs:__imp_OpenThreadToken
0x1800c6b00  nop     dword ptr [rax+rax+00h]
0x1800c6b05  test    eax, eax
0x1800c6b07  jnz     short loc_1800C6B6B
0x1800c6b09  call    cs:__imp_GetLastError
0x1800c6b10  nop     dword ptr [rax+rax+00h]
0x1800c6b15  cmp     eax, 3F0h
0x1800c6b1a  jz      loc_1800C6BAA
0x1800c6b20  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c6b27  lea     rax, WPP_GLOBAL_Control
0x1800c6b2e  cmp     rcx, rax
0x1800c6b31  jz      loc_1800C6BBA
0x1800c6b37  test    dword ptr [rcx+1Ch], 200h
0x1800c6b3e  jz      short loc_1800C6BBA
0x1800c6b40  call    cs:__imp_GetLastError
0x1800c6b47  nop     dword ptr [rax+rax+00h]
0x1800c6b4c  mov     edx, r14d
0x1800c6b4f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c6b56  lea     r8, WPP_b63808fa0c5238d38dcfcce171ba8ec4_Traceguids
0x1800c6b5d  mov     r9d, eax
0x1800c6b60  mov     rcx, [rcx+10h]
0x1800c6b64  call    WPP_SF_d
0x1800c6b69  jmp     short loc_1800C6BBA
0x1800c6b6b  call    cs:__imp_RevertToSelf
0x1800c6b72  nop     dword ptr [rax+rax+00h]
0x1800c6b77  test    eax, eax
0x1800c6b79  jnz     short loc_1800C6BAA
0x1800c6b7b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c6b82  lea     rax, WPP_GLOBAL_Control
0x1800c6b89  cmp     rcx, rax
0x1800c6b8c  jz      short loc_1800C6BBA
0x1800c6b8e  test    dword ptr [rcx+1Ch], 200h
0x1800c6b95  jz      short loc_1800C6BBA
0x1800c6b97  call    cs:__imp_GetLastError
0x1800c6b9e  nop     dword ptr [rax+rax+00h]
0x1800c6ba3  mov     edx, 0Dh
0x1800c6ba8  jmp     short loc_1800C6B4F
0x1800c6baa  shr     esi, 1
0x1800c6bac  mov     rdx, rbx; unsigned __int16 *
0x1800c6baf  mov     r8d, esi; unsigned int
0x1800c6bb2  mov     rcx, r15; pSid
0x1800c6bb5  call    ?LsapUpdateCredentialStuffers@@YAXPEAXPEAGK@Z; LsapUpdateCredentialStuffers(void *,ushort *,ulong)
0x1800c6bba  mov     rdx, [rbp+50h+TokenHandle]; Token
0x1800c6bbe  test    rdx, rdx
0x1800c6bc1  jz      short loc_1800C6BE1
0x1800c6bc3  xor     ecx, ecx; Thread
0x1800c6bc5  call    cs:__imp_SetThreadToken
0x1800c6bcc  nop     dword ptr [rax+rax+00h]
0x1800c6bd1  mov     rcx, [rbp+50h+TokenHandle]; hObject
0x1800c6bd5  call    cs:__imp_CloseHandle
0x1800c6bdc  nop     dword ptr [rax+rax+00h]
0x1800c6be1  test    rbx, rbx
0x1800c6be4  jz      short loc_1800C6C0D
0x1800c6be6  mov     rax, rbx
0x1800c6be9  mov     byte ptr [rax], 0
0x1800c6bec  inc     rax
0x1800c6bef  sub     rdi, 1
0x1800c6bf3  jnz     short loc_1800C6BE9
0x1800c6bf5  lea     rcx, [rbx-8]
0x1800c6bf9  cmp     dword ptr [rcx], 70616548h
0x1800c6bff  jnz     short loc_1800C6C0D
0x1800c6c01  mov     rax, cs:g_pfnFree
0x1800c6c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6c0d  mov     rcx, [rbp+50h+var_40]
0x1800c6c11  xor     rcx, rbp; StackCookie
0x1800c6c14  call    __security_check_cookie
0x1800c6c19  lea     rsp, [rbp+28h]
0x1800c6c1d  pop     r15
0x1800c6c1f  pop     r14
0x1800c6c21  pop     rdi
0x1800c6c22  pop     rsi
0x1800c6c23  pop     rbx
0x1800c6c24  pop     rbp
0x1800c6c25  retn
```
