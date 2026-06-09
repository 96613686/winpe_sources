# RasEntryChangeNotificationCallback

- ea: `0x18003b600`
- end: `0x18003b87f`
- name: `RasEntryChangeNotificationCallback`
- size: `639`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180010d10`
- `0x18003b600`
- `0x18004e580`
- `0x18004e984`
- `0x1800a8800`
- `0x1800a8844`
- `0x1800ded06`
- `0x1800e0010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x18003b77b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x18003b77b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b7a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b7a0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18003b694`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18003b694`

## pseudocode

```c
void __fastcall RasEntryChangeNotificationCallback(__int64 a1, HANDLE *a2, struct _TP_WAIT *a3, unsigned int a4)
{
  __int64 v7; // r8
  _DWORD *v8; // rcx
  unsigned int v9; // eax
  int v10; // edx
  int v11; // r8d
  __int64 v12; // rbx
  DWORD LastError; // eax
  HANDLE v14; // rdx
  __int64 v15; // rdx
  _DWORD v16[76]; // [rsp+30h] [rbp-E98h] BYREF
  char v17[514]; // [rsp+160h] [rbp-D68h] BYREF
  char v18[2918]; // [rsp+362h] [rbp-B66h] BYREF
  ULONG StackSizeInBytes; // [rsp+ED8h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, WPP_a576594392393f475090d0b18cfbf556_Traceguids);
  }
  StackSizeInBytes = 0x10000;
  memset_0(v16, 0, 0xE60u);
  DebugInit();
  if ( a2 && a2[4] )
  {
    SetThreadpoolWait(a3, a2[1], 0);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_l(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, v7, *(unsigned int *)a2);
      v8 = WPP_GLOBAL_Control;
    }
    if ( a4 == 128 || a4 == 258 )
    {
      if ( v8 == (_DWORD *)&WPP_GLOBAL_Control )
        return;
      if ( (v8[7] & 0x800) == 0 || *((_BYTE *)v8 + 25) < 2u )
        goto LABEL_44;
      WPP_SF_l(*((_QWORD *)v8 + 2), 82, v7, a4);
      goto LABEL_43;
    }
    v9 = ((__int64 (__fastcall *)(_QWORD, _DWORD *))g_pRasGetNotificationEntry)(*(unsigned int *)a2, v16);
    if ( v9 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_44;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, WPP_a576594392393f475090d0b18cfbf556_Traceguids, v9);
      goto LABEL_43;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_lSS(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v11, v16[0], (__int64)v18, (__int64)v17);
    }
    if ( !SetThreadStackGuarantee(&StackSizeInBytes) )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      {
        goto LABEL_28;
      }
      v12 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      LastError = GetLastError();
      WPP_SF_d(v12, 85, WPP_a576594392393f475090d0b18cfbf556_Traceguids, LastError);
    }
    v8 = WPP_GLOBAL_Control;
LABEL_28:
    v14 = a2[4];
    if ( v14 )
    {
      ((void (__fastcall *)(_QWORD, HANDLE, _DWORD *, __int64))a2[3])(0, v14, v16, 1);
LABEL_43:
      v8 = WPP_GLOBAL_Control;
      goto LABEL_44;
    }
    if ( v8 == (_DWORD *)&WPP_GLOBAL_Control )
      return;
    if ( (v8[7] & 0x800) == 0 || *((_BYTE *)v8 + 25) < 2u )
      goto LABEL_44;
    v15 = 86;
LABEL_42:
    WPP_SF_(*((_QWORD *)v8 + 2), v15, WPP_a576594392393f475090d0b18cfbf556_Traceguids);
    goto LABEL_43;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v15 = 80;
    goto LABEL_42;
  }
LABEL_44:
  if ( v8 != (_DWORD *)&WPP_GLOBAL_Control && (v8[7] & 0x800) != 0 && *((_BYTE *)v8 + 25) >= 6u )
    WPP_SF_(*((_QWORD *)v8 + 2), 87, WPP_a576594392393f475090d0b18cfbf556_Traceguids);
}

```

## disassembly

```asm
0x18003b600  push    rbx
0x18003b602  push    rbp
0x18003b603  push    rsi
0x18003b604  push    rdi
0x18003b605  push    r14
0x18003b607  push    r15
0x18003b609  sub     rsp, 0E98h
0x18003b610  mov     ebx, r9d
0x18003b613  mov     rsi, r8
0x18003b616  mov     rdi, rdx
0x18003b619  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b620  lea     r14, WPP_GLOBAL_Control
0x18003b627  lea     r15, WPP_a576594392393f475090d0b18cfbf556_Traceguids
0x18003b62e  mov     ebp, 800h
0x18003b633  cmp     rcx, r14
0x18003b636  jz      short loc_18003B654
0x18003b638  test    [rcx+1Ch], ebp
0x18003b63b  jz      short loc_18003B654
0x18003b63d  cmp     byte ptr [rcx+19h], 6
0x18003b641  jb      short loc_18003B654
0x18003b643  mov     rcx, [rcx+10h]
0x18003b647  mov     edx, 4Fh ; 'O'
0x18003b64c  mov     r8, r15
0x18003b64f  call    WPP_SF_
0x18003b654  xor     edx, edx; Val
0x18003b656  mov     [rsp+0EC8h+StackSizeInBytes], 10000h
0x18003b661  mov     r8d, 0E60h; Size
0x18003b667  lea     rcx, [rsp+0EC8h+var_E98]; void *
0x18003b66c  call    memset_0
0x18003b671  call    DebugInit
0x18003b676  test    rdi, rdi
0x18003b679  jz      loc_18003B81F
0x18003b67f  cmp     qword ptr [rdi+20h], 0
0x18003b684  jz      loc_18003B81F
0x18003b68a  mov     rdx, [rdi+8]; h
0x18003b68e  xor     r8d, r8d; pftTimeout
0x18003b691  mov     rcx, rsi; pwa
0x18003b694  call    cs:__imp_SetThreadpoolWait
0x18003b69a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b6a1  cmp     rcx, r14
0x18003b6a4  jz      short loc_18003B6C9
0x18003b6a6  test    [rcx+1Ch], ebp
0x18003b6a9  jz      short loc_18003B6C9
0x18003b6ab  cmp     byte ptr [rcx+19h], 5
0x18003b6af  jb      short loc_18003B6C9
0x18003b6b1  mov     r9d, [rdi]
0x18003b6b4  mov     edx, 51h ; 'Q'
0x18003b6b9  mov     rcx, [rcx+10h]
0x18003b6bd  call    WPP_SF_l
0x18003b6c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b6c9  cmp     ebx, 80h
0x18003b6cf  jz      loc_18003B7FC
0x18003b6d5  cmp     ebx, 102h
0x18003b6db  jz      loc_18003B7FC
0x18003b6e1  mov     ecx, [rdi]
0x18003b6e3  lea     rdx, [rsp+0EC8h+var_E98]
0x18003b6e8  mov     rax, cs:g_pRasGetNotificationEntry
0x18003b6ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b6f4  test    eax, eax
0x18003b6f6  jz      short loc_18003B734
0x18003b6f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b6ff  cmp     rcx, r14
0x18003b702  jz      loc_18003B86F
0x18003b708  test    [rcx+1Ch], ebp
0x18003b70b  jz      loc_18003B84E
0x18003b711  cmp     byte ptr [rcx+19h], 2
0x18003b715  jb      loc_18003B84E
0x18003b71b  mov     rcx, [rcx+10h]
0x18003b71f  mov     edx, 53h ; 'S'
0x18003b724  mov     r9d, eax
0x18003b727  mov     r8, r15
0x18003b72a  call    WPP_SF_d
0x18003b72f  jmp     loc_18003B847
0x18003b734  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b73b  cmp     rcx, r14
0x18003b73e  jz      short loc_18003B773
0x18003b740  test    [rcx+1Ch], ebp
0x18003b743  jz      short loc_18003B773
0x18003b745  cmp     byte ptr [rcx+19h], 5
0x18003b749  jb      short loc_18003B773
0x18003b74b  mov     r9d, [rsp+0EC8h+var_E98]
0x18003b750  lea     rax, [rsp+0EC8h+var_D68]
0x18003b758  mov     rcx, [rcx+10h]
0x18003b75c  mov     [rsp+0EC8h+var_EA0], rax
0x18003b761  lea     rax, [rsp+0EC8h+var_B66]
0x18003b769  mov     [rsp+0EC8h+var_EA8], rax
0x18003b76e  call    WPP_SF_lSS
0x18003b773  lea     rcx, [rsp+0EC8h+StackSizeInBytes]; StackSizeInBytes
0x18003b77b  call    cs:__imp_SetThreadStackGuarantee
0x18003b781  test    eax, eax
0x18003b783  jnz     short loc_18003B7B9
0x18003b785  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b78c  cmp     rcx, r14
0x18003b78f  jz      short loc_18003B7C0
0x18003b791  test    [rcx+1Ch], ebp
0x18003b794  jz      short loc_18003B7C0
0x18003b796  cmp     byte ptr [rcx+19h], 3
0x18003b79a  jb      short loc_18003B7C0
0x18003b79c  mov     rbx, [rcx+10h]
0x18003b7a0  call    cs:__imp_GetLastError
0x18003b7a6  mov     edx, 55h ; 'U'
0x18003b7ab  mov     r8, r15
0x18003b7ae  mov     r9d, eax
0x18003b7b1  mov     rcx, rbx
0x18003b7b4  call    WPP_SF_d
0x18003b7b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b7c0  mov     rdx, [rdi+20h]
0x18003b7c4  test    rdx, rdx
0x18003b7c7  jnz     short loc_18003B7E4
0x18003b7c9  cmp     rcx, r14
0x18003b7cc  jz      loc_18003B86F
0x18003b7d2  test    [rcx+1Ch], ebp
0x18003b7d5  jz      short loc_18003B84E
0x18003b7d7  cmp     byte ptr [rcx+19h], 2
0x18003b7db  jb      short loc_18003B84E
0x18003b7dd  mov     edx, 56h ; 'V'
0x18003b7e2  jmp     short loc_18003B83B
0x18003b7e4  mov     rax, [rdi+18h]
0x18003b7e8  lea     r8, [rsp+0EC8h+var_E98]
0x18003b7ed  mov     r9d, 1
0x18003b7f3  xor     ecx, ecx
0x18003b7f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b7fa  jmp     short loc_18003B847
0x18003b7fc  cmp     rcx, r14
0x18003b7ff  jz      short loc_18003B86F
0x18003b801  test    [rcx+1Ch], ebp
0x18003b804  jz      short loc_18003B84E
0x18003b806  cmp     byte ptr [rcx+19h], 2
0x18003b80a  jb      short loc_18003B84E
0x18003b80c  mov     rcx, [rcx+10h]
0x18003b810  mov     edx, 52h ; 'R'
0x18003b815  mov     r9d, ebx
0x18003b818  call    WPP_SF_l
0x18003b81d  jmp     short loc_18003B847
0x18003b81f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b826  cmp     rcx, r14
0x18003b829  jz      short loc_18003B86F
0x18003b82b  test    [rcx+1Ch], ebp
0x18003b82e  jz      short loc_18003B84E
0x18003b830  cmp     byte ptr [rcx+19h], 2
0x18003b834  jb      short loc_18003B84E
0x18003b836  mov     edx, 50h ; 'P'
0x18003b83b  mov     rcx, [rcx+10h]
0x18003b83f  mov     r8, r15
0x18003b842  call    WPP_SF_
0x18003b847  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b84e  cmp     rcx, r14
0x18003b851  jz      short loc_18003B86F
0x18003b853  test    [rcx+1Ch], ebp
0x18003b856  jz      short loc_18003B86F
0x18003b858  cmp     byte ptr [rcx+19h], 6
0x18003b85c  jb      short loc_18003B86F
0x18003b85e  mov     rcx, [rcx+10h]
0x18003b862  mov     edx, 57h ; 'W'
0x18003b867  mov     r8, r15
0x18003b86a  call    WPP_SF_
0x18003b86f  add     rsp, 0E98h
0x18003b876  pop     r15
0x18003b878  pop     r14
0x18003b87a  pop     rdi
0x18003b87b  pop     rsi
0x18003b87c  pop     rbp
0x18003b87d  pop     rbx
0x18003b87e  retn
```
