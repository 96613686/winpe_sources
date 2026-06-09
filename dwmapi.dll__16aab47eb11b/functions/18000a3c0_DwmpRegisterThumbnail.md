# DwmpRegisterThumbnail

- ea: `0x18000a3c0`
- end: `0x18000a51e`
- name: `DwmpRegisterThumbnail`
- size: `350`
- prototype: `__int64 __usercall@<rax>(HWND hWnd@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x180013bd0`

## callees

- `0x180001520`
- `0x18000352c`
- `0x18000a3c0`
- `0x18000ad58`
- `0x18000b990`
- `0x18000bab0`
- `0x18000d0a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a459`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a459`
- `USER32!IsTopLevelWindow` at `0x18000a3f3`
- `USER32!IsTopLevelWindow` at `0x18000a404`
- `USER32!IsTopLevelWindow` at `0x18000a3f3`
- `USER32!IsTopLevelWindow` at `0x18000a404`

## pseudocode

```c
__int64 __fastcall DwmpRegisterThumbnail(HWND hWnd, HWND a2, int a3, int a4, _QWORD *a5)
{
  unsigned __int32 v9; // esi
  CApiPortClient *v10; // rcx
  int v11; // ebx
  void *v13; // [rsp+28h] [rbp-58h]
  int v14; // [rsp+30h] [rbp-50h] BYREF
  void **v15; // [rsp+38h] [rbp-48h] BYREF
  __int128 v16; // [rsp+40h] [rbp-40h] BYREF
  int v17[3]; // [rsp+50h] [rbp-30h] BYREF
  HWND v18; // [rsp+5Ch] [rbp-24h]
  HWND v19; // [rsp+64h] [rbp-1Ch]
  int v20; // [rsp+6Ch] [rbp-14h]
  int v21; // [rsp+70h] [rbp-10h]

  if ( (unsigned int)IsTopLevelWindow(hWnd) && (unsigned int)IsTopLevelWindow(a2) && hWnd != a2 && IsHwndInProcess(hWnd) )
  {
    v9 = _InterlockedIncrement(&dword_18001F990);
    v17[0] = 1073741855;
    v18 = hWnd;
    v19 = a2;
    v20 = a3;
    v21 = a4;
    v17[1] = v9;
    v17[2] = GetCurrentProcessId();
    v14 = 0;
    v15 = &CStandardData::`vftable';
    v16 = 0;
    v11 = CApiPortClient::SendRequestValidate(v10, v17, 0x24u, (const struct CExtraData *)&v15, &v14);
    v15 = &CStandardData::`vftable';
    if ( (_QWORD)v16 )
      CApiPortClient::UnlockExtraDataPointer((CApiPortClient *)v16);
    std::unique_ptr<CAlpcView>::~unique_ptr<CAlpcView>((char *)&v16 + 8);
    if ( v11 < 0 )
    {
      MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_180019648, 2u, v11, 0x74u, v13);
    }
    else
    {
      v11 = v14;
      if ( v14 >= 0 )
        *a5 = v9;
    }
  }
  else
  {
    v11 = -2147024809;
    MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_180019648, 2u, -2147024809, 0x64u, v13);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000a3c0  push    rbp
0x18000a3c2  push    rbx
0x18000a3c3  push    rsi
0x18000a3c4  push    rdi
0x18000a3c5  push    r12
0x18000a3c7  push    r14
0x18000a3c9  push    r15
0x18000a3cb  mov     rbp, rsp
0x18000a3ce  sub     rsp, 80h
0x18000a3d5  mov     rax, cs:__security_cookie
0x18000a3dc  xor     rax, rsp
0x18000a3df  mov     [rbp+var_8], rax
0x18000a3e3  mov     r14, [rbp+arg_20]
0x18000a3e7  mov     r12d, r9d
0x18000a3ea  mov     r15d, r8d
0x18000a3ed  mov     rdi, rdx
0x18000a3f0  mov     rbx, rcx
0x18000a3f3  call    cs:__imp_IsTopLevelWindow
0x18000a3f9  test    eax, eax
0x18000a3fb  jz      loc_18000A4D8
0x18000a401  mov     rcx, rdi
0x18000a404  call    cs:__imp_IsTopLevelWindow
0x18000a40a  test    eax, eax
0x18000a40c  jz      loc_18000A4D8
0x18000a412  cmp     rbx, rdi
0x18000a415  jz      loc_18000A4D8
0x18000a41b  mov     rcx, rbx; hWnd
0x18000a41e  call    ?IsHwndInProcess@@YA_NPEAUHWND__@@@Z; IsHwndInProcess(HWND__ *)
0x18000a423  test    al, al
0x18000a425  jz      loc_18000A4D8
0x18000a42b  mov     esi, 1
0x18000a430  lock xadd cs:dword_18001F990, esi
0x18000a438  inc     esi
0x18000a43a  mov     [rbp+var_2C], 0
0x18000a442  mov     [rbp+var_30], 4000001Fh
0x18000a449  mov     [rbp+var_24], rbx
0x18000a44d  mov     [rbp+var_1C], rdi
0x18000a451  mov     [rbp+var_14], r15d
0x18000a455  mov     [rbp+var_10], r12d
0x18000a459  call    cs:__imp_GetCurrentProcessId
0x18000a45f  xorps   xmm0, xmm0
0x18000a462  mov     dword ptr [rbp+var_2C], esi
0x18000a465  mov     dword ptr [rbp+var_2C+4], eax
0x18000a468  lea     rdi, ??_7CStandardData@@6B@; const CStandardData::`vftable'
0x18000a46f  lea     rax, [rbp+var_50]
0x18000a473  mov     [rbp+var_50], 0
0x18000a47a  lea     r9, [rbp+var_48]; struct CExtraData *
0x18000a47e  mov     [rsp+80h+var_60], rax; int *
0x18000a483  mov     r8d, 24h ; '$'; unsigned __int64
0x18000a489  mov     [rbp+var_48], rdi
0x18000a48d  lea     rdx, [rbp+var_30]; void *
0x18000a491  movdqu  [rbp+var_40], xmm0
0x18000a496  call    ?SendRequestValidate@CApiPortClient@@QEAAJPEAX_KAEBVCExtraData@@PEAJ@Z; CApiPortClient::SendRequestValidate(void *,unsigned __int64,CExtraData const &,long *)
0x18000a49b  mov     rcx, qword ptr [rbp+var_40]
0x18000a49f  mov     ebx, eax
0x18000a4a1  mov     [rbp+var_48], rdi
0x18000a4a5  test    rcx, rcx
0x18000a4a8  jz      short loc_18000A4B3
0x18000a4aa  lea     rdx, [rbp+var_40+8]
0x18000a4ae  call    ?UnlockExtraDataPointer@CApiPortClient@@QEAAX$$QEAV?$unique_ptr@VCAlpcView@@U?$default_delete@VCAlpcView@@@std@@@std@@@Z; CApiPortClient::UnlockExtraDataPointer(std::unique_ptr<CAlpcView> &&)
0x18000a4b3  lea     rcx, [rbp+var_40+8]
0x18000a4b7  call    ??1?$unique_ptr@VCAlpcView@@U?$default_delete@VCAlpcView@@@std@@@std@@QEAA@XZ; std::unique_ptr<CAlpcView>::~unique_ptr<CAlpcView>(void)
0x18000a4bc  test    ebx, ebx
0x18000a4be  js      short loc_18000A4CE
0x18000a4c0  mov     ebx, [rbp+var_50]
0x18000a4c3  test    ebx, ebx
0x18000a4c5  js      short loc_18000A4FE
0x18000a4c7  mov     eax, esi
0x18000a4c9  mov     [r14], rax
0x18000a4cc  jmp     short loc_18000A4FE
0x18000a4ce  mov     dword ptr [rsp+80h+var_60], 74h ; 't'
0x18000a4d6  jmp     short loc_18000A4E5
0x18000a4d8  mov     ebx, 80070057h
0x18000a4dd  mov     dword ptr [rsp+80h+var_60], 64h ; 'd'; unsigned int
0x18000a4e5  mov     r8d, 2; unsigned int
0x18000a4eb  lea     rdx, qword_180019648; int *
0x18000a4f2  mov     r9d, ebx; int
0x18000a4f5  lea     ecx, [r8+2]; unsigned int
0x18000a4f9  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18000a4fe  mov     eax, ebx
0x18000a500  mov     rcx, [rbp+var_8]
0x18000a504  xor     rcx, rsp; StackCookie
0x18000a507  call    __security_check_cookie
0x18000a50c  add     rsp, 80h
0x18000a513  pop     r15
0x18000a515  pop     r14
0x18000a517  pop     r12
0x18000a519  pop     rdi
0x18000a51a  pop     rsi
0x18000a51b  pop     rbx
0x18000a51c  pop     rbp
0x18000a51d  retn
```
