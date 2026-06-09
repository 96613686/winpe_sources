# ReadIcon

- ea: `0x18000879c`
- end: `0x1800088cb`
- name: `ReadIcon`
- size: `303`
- prototype: `__int64 __fastcall(__int64, CSmartIcon *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800083b8`

## callees

- `0x1800079e0`
- `0x180007aac`
- `0x180007b88`
- `0x180007cb8`
- `0x18000879c`
- `0x180009ac0`
- `0x180009b58`
- `0x18000a5b0`
- `0x18000b010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000888f`
- `KERNEL32!GetLastError` at `0x18000888f`
- `ole32!CLSIDFromString` at `0x1800087e1`
- `ole32!CLSIDFromString` at `0x1800087e1`

## pseudocode

```c
__int64 __fastcall ReadIcon(__int64 a1, CSmartIcon *a2)
{
  __int64 v4; // rcx
  int v5; // ebx
  __int64 result; // rax
  __int64 v7; // rdi
  HICON Icon; // rax
  bool v9; // si
  signed int LastError; // eax
  __int64 v11; // [rsp+20h] [rbp-28h] BYREF
  GUID pclsid; // [rsp+28h] [rbp-20h] BYREF

  if ( IsWhistler() )
  {
    pclsid = 0;
    v5 = CLSIDFromString(L"{46eb5926-582e-4017-9fdf-e8998daa0950}", &pclsid);
    if ( v5 < 0 )
      return (unsigned int)v5;
    v11 = 0;
    v5 = IsolationAwareImageList_ReadEx(v4, a1, &pclsid, &v11);
    if ( v5 < 0 )
    {
      if ( v11 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      return (unsigned int)v5;
    }
    v7 = v11;
    v11 = 0;
  }
  else
  {
    v5 = 0;
    v7 = IsolationAwareImageList_Read(a1);
    if ( !v7 )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( v5 >= 0 )
        return (unsigned int)-2147467259;
      return (unsigned int)v5;
    }
  }
  if ( !v7 )
    return (unsigned int)v5;
  Icon = (HICON)IsolationAwareImageList_GetIcon(v7);
  CSmartIcon::Attach(a2, Icon);
  v9 = *(_QWORD *)a2 && **(_QWORD **)a2;
  IsolationAwareImageList_Destroy(v7);
  result = 0;
  if ( !v9 )
    return (unsigned int)v5;
  return result;
}

```

## disassembly

```asm
0x18000879c  mov     [rsp+arg_10], rbx
0x1800087a1  mov     [rsp+arg_18], rsi
0x1800087a6  push    rdi
0x1800087a7  sub     rsp, 40h
0x1800087ab  mov     rax, cs:__security_cookie
0x1800087b2  xor     rax, rsp
0x1800087b5  mov     [rsp+48h+var_10], rax
0x1800087ba  mov     rsi, rdx
0x1800087bd  mov     rdi, rcx
0x1800087c0  call    ?IsWhistler@@YA_NXZ; IsWhistler(void)
0x1800087c5  test    al, al
0x1800087c7  jz      loc_18000887D
0x1800087cd  xorps   xmm0, xmm0
0x1800087d0  movups  xmmword ptr [rsp+48h+pclsid.Data1], xmm0
0x1800087d5  lea     rdx, [rsp+48h+pclsid]; pclsid
0x1800087da  lea     rcx, sz; "{46eb5926-582e-4017-9fdf-e8998daa0950}"
0x1800087e1  call    cs:__imp_CLSIDFromString
0x1800087e7  mov     ebx, eax
0x1800087e9  test    eax, eax
0x1800087eb  js      short loc_180008825
0x1800087ed  mov     [rsp+48h+var_28], 0
0x1800087f6  lea     r9, [rsp+48h+var_28]
0x1800087fb  lea     r8, [rsp+48h+pclsid]
0x180008800  mov     rdx, rdi
0x180008803  call    IsolationAwareImageList_ReadEx
0x180008808  mov     ebx, eax
0x18000880a  test    eax, eax
0x18000880c  jns     short loc_180008844
0x18000880e  mov     rcx, [rsp+48h+var_28]
0x180008813  test    rcx, rcx
0x180008816  jz      short loc_180008825
0x180008818  mov     rax, [rcx]
0x18000881b  mov     rax, [rax+10h]
0x18000881f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008824  nop
0x180008825  mov     eax, ebx
0x180008827  mov     rcx, [rsp+48h+var_10]
0x18000882c  xor     rcx, rsp; StackCookie
0x18000882f  call    __security_check_cookie
0x180008834  mov     rbx, [rsp+48h+arg_10]
0x180008839  mov     rsi, [rsp+48h+arg_18]
0x18000883e  add     rsp, 40h
0x180008842  pop     rdi
0x180008843  retn
0x180008844  mov     rdi, [rsp+48h+var_28]
0x180008849  mov     [rsp+48h+var_28], 0
0x180008852  test    rdi, rdi
0x180008855  jz      short loc_180008825
0x180008857  mov     rcx, rdi
0x18000885a  call    IsolationAwareImageList_GetIcon
0x18000885f  mov     rdx, rax; HICON
0x180008862  mov     rcx, rsi; this
0x180008865  call    ?Attach@CSmartIcon@@QEAAXPEAUHICON__@@@Z; CSmartIcon::Attach(HICON__ *)
0x18000886a  mov     rax, [rsi]
0x18000886d  test    rax, rax
0x180008870  jz      short loc_1800088B3
0x180008872  cmp     qword ptr [rax], 0
0x180008876  jz      short loc_1800088B3
0x180008878  mov     sil, 1
0x18000887b  jmp     short loc_1800088B6
0x18000887d  xor     ebx, ebx
0x18000887f  mov     rcx, rdi
0x180008882  call    IsolationAwareImageList_Read
0x180008887  mov     rdi, rax
0x18000888a  test    rax, rax
0x18000888d  jnz     short loc_180008852
0x18000888f  call    cs:__imp_GetLastError
0x180008895  mov     ebx, eax
0x180008897  test    eax, eax
0x180008899  jle     short loc_1800088A4
0x18000889b  movzx   ebx, ax
0x18000889e  or      ebx, 80070000h
0x1800088a4  mov     eax, 80004005h
0x1800088a9  test    ebx, ebx
0x1800088ab  cmovns  ebx, eax
0x1800088ae  jmp     loc_180008825
0x1800088b3  xor     sil, sil
0x1800088b6  mov     rcx, rdi
0x1800088b9  call    IsolationAwareImageList_Destroy
0x1800088be  xor     eax, eax
0x1800088c0  test    sil, sil
0x1800088c3  cmovz   eax, ebx
0x1800088c6  jmp     loc_180008827
```
