# FTPHOST_CLASS::GetCOMObject(ushort const *,_GUID const &,tagSAFEARRAY *,IUnknown * *)

- ea: `0x1800034d0`
- end: `0x180003621`
- name: `?GetCOMObject@FTPHOST_CLASS@@UEAAJPEBGAEBU_GUID@@PEAUtagSAFEARRAY@@PEAPEAUIUnknown@@@Z`
- size: `337`
- prototype: `__int64 __fastcall(FTPHOST_CLASS *this, const unsigned __int16 *, const struct _GUID *, struct tagSAFEARRAY *, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800034d0`
- `0x180004420`
- `0x180005010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000358a`
- `ole32!CoCreateInstance` at `0x18000358a`
- `ole32!CLSIDFromProgID` at `0x180003526`
- `ole32!CLSIDFromProgID` at `0x180003526`
- `ole32!CLSIDFromString` at `0x180003514`
- `ole32!CLSIDFromString` at `0x180003514`
- `iisutil!PuDbgPrintError` at `0x18000356f`
- `iisutil!PuDbgPrintError` at `0x18000356f`

## string_xrefs

- `0x18000353f`: `Couldn't resolve %S to CLSID\n`
- `0x180003553`: `FTPHOST_CLASS::GetCOMObject`
- `0x18000359f`: `CoCreateInstance on %S failed\n`

## pseudocode

```c
__int64 __fastcall FTPHOST_CLASS::GetCOMObject(
        FTPHOST_CLASS *this,
        const unsigned __int16 *a2,
        const struct _GUID *a3,
        struct tagSAFEARRAY *a4,
        LPVOID *ppv)
{
  HRESULT v8; // ebx
  const char *v9; // rax
  __int64 v10; // r8
  int v11; // eax
  __int64 v13; // [rsp+40h] [rbp-48h] BYREF
  CLSID pclsid; // [rsp+48h] [rbp-40h] BYREF

  v13 = 0;
  pclsid = 0;
  if ( CLSIDFromString(a2, &pclsid) )
  {
    v8 = CLSIDFromProgID(a2, &pclsid);
    if ( v8 )
    {
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_13;
      v9 = "Couldn't resolve %S to CLSID\n";
      v10 = 349;
      goto LABEL_5;
    }
  }
  v8 = CoCreateInstance(&pclsid, 0, 1u, a3, ppv);
  if ( v8 >= 0 )
  {
    v11 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))*ppv)(
            *ppv,
            &GUID_4d1a3f7b_412d_447c_b199_64f967e9a2da,
            &v13);
    v8 = v11;
    if ( v11 == -2147467262
      || v11 >= 0
      && (v8 = (*(__int64 (__fastcall **)(__int64, struct tagSAFEARRAY *))(*(_QWORD *)v13 + 24LL))(v13, a4), v8 >= 0) )
    {
      v8 = 0;
    }
  }
  else if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    v9 = "CoCreateInstance on %S failed\n";
    v10 = 371;
LABEL_5:
    PuDbgPrintError(
      g_pDebug,
      "inetsrv\\iis\\iisrearc\\ftp\\server\\extensibility\\ftphost\\ftphost_class.cxx",
      v10,
      "FTPHOST_CLASS::GetCOMObject",
      v8,
      v9,
      a2);
  }
LABEL_13:
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800034d0  push    rbx
0x1800034d2  push    rbp
0x1800034d3  push    rsi
0x1800034d4  push    rdi
0x1800034d5  push    r14
0x1800034d7  sub     rsp, 60h
0x1800034db  mov     rax, cs:__security_cookie
0x1800034e2  xor     rax, rsp
0x1800034e5  mov     [rsp+88h+var_30], rax
0x1800034ea  mov     rsi, [rsp+88h+arg_20]
0x1800034f2  mov     rdi, rdx
0x1800034f5  xorps   xmm0, xmm0
0x1800034f8  mov     [rsp+88h+var_48], 0
0x180003501  mov     rcx, rdi; lpsz
0x180003504  lea     rdx, [rsp+88h+pclsid]; pclsid
0x180003509  mov     r14, r9
0x18000350c  mov     rbp, r8
0x18000350f  movups  xmmword ptr [rsp+88h+pclsid.Data1], xmm0
0x180003514  call    cs:__imp_CLSIDFromString
0x18000351a  test    eax, eax
0x18000351c  jz      short loc_180003577
0x18000351e  lea     rdx, [rsp+88h+pclsid]; lpclsid
0x180003523  mov     rcx, rdi; lpszProgID
0x180003526  call    cs:__imp_CLSIDFromProgID
0x18000352c  mov     ebx, eax
0x18000352e  test    eax, eax
0x180003530  jz      short loc_180003577
0x180003532  test    cs:g_dwDebugFlags, 0Fh
0x180003539  jz      loc_1800035F1
0x18000353f  lea     rax, aCouldnTResolve; "Couldn't resolve %S to CLSID\n"
0x180003546  mov     r8d, 15Dh
0x18000354c  mov     rcx, cs:g_pDebug
0x180003553  lea     r9, aFtphostClassGe_0; "FTPHOST_CLASS::GetCOMObject"
0x18000355a  mov     [rsp+88h+var_58], rdi
0x18000355f  lea     rdx, aInetsrvIisIisr_0; "inetsrv\\iis\\iisrearc\\ftp\\server\\ex"...
0x180003566  mov     [rsp+88h+var_60], rax
0x18000356b  mov     dword ptr [rsp+88h+ppv], ebx
0x18000356f  call    cs:__imp_PuDbgPrintError
0x180003575  jmp     short loc_1800035F1
0x180003577  xor     edx, edx; pUnkOuter
0x180003579  mov     [rsp+88h+ppv], rsi; ppv
0x18000357e  mov     r9, rbp; riid
0x180003581  lea     rcx, [rsp+88h+pclsid]; rclsid
0x180003586  lea     r8d, [rdx+1]; dwClsContext
0x18000358a  call    cs:__imp_CoCreateInstance
0x180003590  mov     ebx, eax
0x180003592  test    eax, eax
0x180003594  jns     short loc_1800035AE
0x180003596  test    cs:g_dwDebugFlags, 0Fh
0x18000359d  jz      short loc_1800035F1
0x18000359f  lea     rax, aCocreateinstan; "CoCreateInstance on %S failed\n"
0x1800035a6  mov     r8d, 173h
0x1800035ac  jmp     short loc_18000354C
0x1800035ae  mov     rcx, [rsi]
0x1800035b1  lea     r8, [rsp+88h+var_48]
0x1800035b6  lea     rdx, _GUID_4d1a3f7b_412d_447c_b199_64f967e9a2da
0x1800035bd  mov     rax, [rcx]
0x1800035c0  mov     rax, [rax]
0x1800035c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035c8  mov     ebx, eax
0x1800035ca  cmp     eax, 80004002h
0x1800035cf  jz      short loc_1800035EF
0x1800035d1  test    eax, eax
0x1800035d3  js      short loc_1800035F1
0x1800035d5  mov     rcx, [rsp+88h+var_48]
0x1800035da  mov     rdx, r14
0x1800035dd  mov     rax, [rcx]
0x1800035e0  mov     rax, [rax+18h]
0x1800035e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035e9  mov     ebx, eax
0x1800035eb  test    eax, eax
0x1800035ed  js      short loc_1800035F1
0x1800035ef  xor     ebx, ebx
0x1800035f1  mov     rcx, [rsp+88h+var_48]
0x1800035f6  test    rcx, rcx
0x1800035f9  jz      short loc_180003607
0x1800035fb  mov     rax, [rcx]
0x1800035fe  mov     rax, [rax+10h]
0x180003602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003607  mov     eax, ebx
0x180003609  mov     rcx, [rsp+88h+var_30]
0x18000360e  xor     rcx, rsp; StackCookie
0x180003611  call    __security_check_cookie
0x180003616  add     rsp, 60h
0x18000361a  pop     r14
0x18000361c  pop     rdi
0x18000361d  pop     rsi
0x18000361e  pop     rbp
0x18000361f  pop     rbx
0x180003620  retn
```
