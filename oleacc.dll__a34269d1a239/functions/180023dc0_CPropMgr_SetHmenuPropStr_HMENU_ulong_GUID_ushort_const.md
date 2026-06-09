# CPropMgr::SetHmenuPropStr(HMENU__ *,ulong,_GUID,ushort const *)

- ea: `0x180023dc0`
- end: `0x180023eb6`
- name: `?SetHmenuPropStr@CPropMgr@@UEAAJPEAUHMENU__@@KU_GUID@@PEBG@Z`
- size: `246`
- prototype: `__int64 __fastcall(CPropMgr *__hidden this, HMENU, unsigned int, struct _GUID *, OLECHAR *psz)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x180010d94`
- `0x180019610`
- `0x18001a2a4`
- `0x18001e4c0`
- `0x180023dc0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180023e42`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180023e42`
- `OLEAUT32!__imp_SysAllocString` at `0x180023e2c`
- `OLEAUT32!__imp_SysAllocString` at `0x180023e2c`
- `OLEAUT32!__imp_SysFreeString` at `0x180023e88`
- `OLEAUT32!__imp_SysFreeString` at `0x180023e88`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPropMgr::SetHmenuPropStr(CPropMgrImpl **this, HMENU a2, int a3, struct _GUID *a4, OLECHAR *psz)
{
  int v7; // esi
  unsigned int v9; // ebx
  DWORD CurrentProcessId; // eax
  struct tagVARIANT bstrString; // [rsp+30h] [rbp-41h] BYREF
  struct _GUID v13; // [rsp+50h] [rbp-21h] BYREF
  unsigned __int8 v14[24]; // [rsp+60h] [rbp-11h] BYREF
  unsigned __int8 v15[4]; // [rsp+78h] [rbp+7h] BYREF
  DWORD v16; // [rsp+7Ch] [rbp+Bh]
  int v17; // [rsp+80h] [rbp+Fh]
  int v18; // [rsp+84h] [rbp+13h]

  v7 = (int)a2;
  OleaccApiCallTrace::OleaccApiCallTrace(v14, 1011, this);
  if ( this[2] )
  {
    *(_QWORD *)&bstrString.vt = 8;
    *(_OWORD *)&bstrString.decVal.Lo32 = (unsigned __int64)SysAllocString(psz);
    if ( bstrString.llVal )
    {
      CurrentProcessId = GetCurrentProcessId();
      *(_DWORD *)v15 = -2147483646;
      v16 = CurrentProcessId;
      v17 = v7;
      v18 = a3;
      v13 = *a4;
      v9 = CPropMgrImpl::SetPropValue(this[2], v15, 16, &v13, &bstrString);
      SysFreeString(bstrString.bstrVal);
    }
    else
    {
      v9 = -2147024882;
    }
  }
  else
  {
    v9 = -2147467259;
  }
  OleaccApiCallTrace::~OleaccApiCallTrace((OleaccApiCallTrace *)v14);
  return v9;
}

```

## disassembly

```asm
0x180023dc0  push    rbp
0x180023dc2  push    rbx
0x180023dc3  push    rsi
0x180023dc4  push    rdi
0x180023dc5  push    r14
0x180023dc7  push    r15
0x180023dc9  lea     rbp, [rsp-27h]
0x180023dce  sub     rsp, 98h
0x180023dd5  mov     rax, cs:__security_cookie
0x180023ddc  xor     rax, rsp
0x180023ddf  mov     [rbp+4Fh+var_38], rax
0x180023de3  mov     r15, r9
0x180023de6  mov     r14d, r8d
0x180023de9  mov     rsi, rdx
0x180023dec  mov     rbx, rcx
0x180023def  mov     rdi, [rbp+4Fh+psz]
0x180023df3  mov     r8, rcx
0x180023df6  mov     edx, 3F3h
0x180023dfb  lea     rcx, [rbp+4Fh+var_60]
0x180023dff  call    ??0OleaccApiCallTrace@@QEAA@W4OLEACC_API_ENTRYPOINT@@PEAX@Z; OleaccApiCallTrace::OleaccApiCallTrace(OLEACC_API_ENTRYPOINT,void *)
0x180023e04  nop
0x180023e05  cmp     qword ptr [rbx+10h], 0
0x180023e0a  jnz     short loc_180023E13
0x180023e0c  mov     ebx, 80004005h
0x180023e11  jmp     short loc_180023E8F
0x180023e13  xorps   xmm0, xmm0
0x180023e16  xor     eax, eax
0x180023e18  movups  xmmword ptr [rbp+4Fh+bstrString], xmm0
0x180023e1c  mov     [rbp+4Fh+var_80], rax
0x180023e20  mov     eax, 8
0x180023e25  mov     word ptr [rbp+4Fh+bstrString], ax
0x180023e29  mov     rcx, rdi; psz
0x180023e2c  call    cs:__imp_SysAllocString
0x180023e32  mov     [rbp+4Fh+bstrString+8], rax
0x180023e36  test    rax, rax
0x180023e39  jnz     short loc_180023E42
0x180023e3b  mov     ebx, 8007000Eh
0x180023e40  jmp     short loc_180023E8F
0x180023e42  call    cs:__imp_GetCurrentProcessId
0x180023e48  mov     dword ptr [rbp+4Fh+var_48], 80000002h
0x180023e4f  mov     [rbp+4Fh+var_44], eax
0x180023e52  mov     [rbp+4Fh+var_40], esi
0x180023e55  mov     [rbp+4Fh+var_3C], r14d
0x180023e59  movups  xmm0, xmmword ptr [r15]
0x180023e5d  movdqu  xmmword ptr [rbp+4Fh+var_70.Data1], xmm0
0x180023e62  lea     rax, [rbp+4Fh+bstrString]
0x180023e66  mov     [rsp+0C0h+var_A0], rax; struct tagVARIANT *
0x180023e6b  lea     r9, [rbp+4Fh+var_70]; struct _GUID
0x180023e6f  mov     r8d, 10h; unsigned int
0x180023e75  lea     rdx, [rbp+4Fh+var_48]; unsigned __int8 *
0x180023e79  mov     rcx, [rbx+10h]; this
0x180023e7d  call    ?SetPropValue@CPropMgrImpl@@QEAAJPEBEKU_GUID@@PEAUtagVARIANT@@@Z; CPropMgrImpl::SetPropValue(uchar const *,ulong,_GUID,tagVARIANT *)
0x180023e82  mov     ebx, eax
0x180023e84  mov     rcx, [rbp+4Fh+bstrString+8]; bstrString
0x180023e88  call    cs:__imp_SysFreeString
0x180023e8e  nop
0x180023e8f  lea     rcx, [rbp+4Fh+var_60]; this
0x180023e93  call    ??1OleaccApiCallTrace@@QEAA@XZ; OleaccApiCallTrace::~OleaccApiCallTrace(void)
0x180023e98  mov     eax, ebx
0x180023e9a  mov     rcx, [rbp+4Fh+var_38]
0x180023e9e  xor     rcx, rsp; StackCookie
0x180023ea1  call    __security_check_cookie
0x180023ea6  add     rsp, 98h
0x180023ead  pop     r15
0x180023eaf  pop     r14
0x180023eb1  pop     rdi
0x180023eb2  pop     rsi
0x180023eb3  pop     rbx
0x180023eb4  pop     rbp
0x180023eb5  retn
```
