# CLSIDFromAtomWithTreatAs(ushort *,_GUID *,CNVTYP *)

- ea: `0x18007702c`
- end: `0x180077130`
- name: `?CLSIDFromAtomWithTreatAs@@YAJPEAGPEAU_GUID@@PEAW4CNVTYP@@@Z`
- size: `260`
- prototype: `HRESULT __fastcall(unsigned __int16 *paClass, _GUID *pclsid, CNVTYP *pcnvtyp)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800293c0`
- `0x1800743c0`

## callees

- `0x180046460`
- `0x180076f88`
- `0x18007702c`
- `0x18009a3a0`

## import_xrefs

- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x1800770e8`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x1800770e8`
- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x1800770d1`
- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x1800770d1`
- `api-ms-win-core-com-l1-1-0!CoGetTreatAsClass` at `0x18007707b`
- `api-ms-win-core-com-l1-1-0!CoGetTreatAsClass` at `0x18007707b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180077106`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180077106`

## pseudocode

```c
__int64 __fastcall CLSIDFromAtomWithTreatAs(unsigned __int16 *paClass, _GUID *pclsid, CNVTYP *pcnvtyp)
{
  unsigned __int16 v4; // cx
  HRESULT v7; // edi
  bool v8; // r8
  ATOM v9; // ax
  _GUID v10; // xmm0
  wchar_t *v11; // rcx
  wchar_t *szProgID; // [rsp+20h] [rbp-38h] BYREF
  _GUID clsidNew; // [rsp+28h] [rbp-30h] BYREF

  szProgID = 0;
  v4 = *paClass;
  clsidNew = 0;
  if ( CLSIDFromAtom(v4, pclsid) )
  {
    if ( CoGetTreatAsClass(pclsid, &clsidNew) )
    {
      if ( (unsigned int)OleGetAutoConvertInternal(pclsid, &clsidNew, v8) )
      {
        if ( pcnvtyp )
          *pcnvtyp = cnvtypNone;
        clsidNew = *pclsid;
      }
      else if ( pcnvtyp )
      {
        *pcnvtyp = cnvtypConvertTo;
      }
    }
    else if ( pcnvtyp )
    {
      *pcnvtyp = cnvtypTreatAs;
    }
    v7 = ProgIDFromCLSID(&clsidNew, &szProgID);
    if ( v7 >= 0 )
    {
      v9 = GlobalAddAtomW(szProgID);
      v10 = clsidNew;
      v11 = szProgID;
      *paClass = v9;
      *pclsid = v10;
      CoTaskMemFree(v11);
    }
  }
  else
  {
    return 1;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18007702c  mov     [rsp+arg_18], rbx
0x180077031  push    rsi
0x180077032  push    rdi
0x180077033  push    r14
0x180077035  sub     rsp, 40h
0x180077039  mov     rax, cs:__security_cookie
0x180077040  xor     rax, rsp
0x180077043  mov     [rsp+58h+var_20], rax
0x180077048  and     [rsp+58h+szProgID], 0
0x18007704e  mov     r14, paClass
0x180077051  movzx   ecx, word ptr [paClass]; aClass
0x180077054  xorps   xmm0, xmm0
0x180077057  movups  xmmword ptr [rsp+58h+clsidNew.Data1], xmm0
0x18007705c  mov     rbx, pcnvtyp
0x18007705f  mov     rsi, pclsid
0x180077062  call    ?CLSIDFromAtom@@YAHGPEAU_GUID@@@Z; CLSIDFromAtom(ushort,_GUID *)
0x180077067  test    eax, eax
0x180077069  jnz     short loc_180077073
0x18007706b  lea     edi, [rax+1]
0x18007706e  jmp     $exitRtn_15
0x180077073  lea     pclsid, [rsp+58h+clsidNew]; pClsidNew
0x180077078  mov     paClass, rsi; clsidOld
0x18007707b  call    cs:__imp_CoGetTreatAsClass
0x180077082  nop     dword ptr [rax+rax+00h]
0x180077087  test    eax, eax
0x180077089  jnz     short loc_180077098
0x18007708b  test    rbx, rbx
0x18007708e  jz      short loc_1800770C7
0x180077090  mov     dword ptr [rbx], 2
0x180077096  jmp     short loc_1800770C7
0x180077098  lea     pclsid, [rsp+58h+clsidNew]; pClsidNew
0x18007709d  mov     paClass, rsi; clsidOld
0x1800770a0  call    ?OleGetAutoConvertInternal@@YAJAEBU_GUID@@PEAU1@_N@Z; OleGetAutoConvertInternal(_GUID const &,_GUID *,bool)
0x1800770a5  test    eax, eax
0x1800770a7  jnz     short loc_1800770B6
0x1800770a9  test    rbx, rbx
0x1800770ac  jz      short loc_1800770C7
0x1800770ae  mov     dword ptr [rbx], 1
0x1800770b4  jmp     short loc_1800770C7
0x1800770b6  test    rbx, rbx
0x1800770b9  jz      short loc_1800770BE
0x1800770bb  and     dword ptr [rbx], 0
0x1800770be  movups  xmm0, xmmword ptr [rsi]
0x1800770c1  movdqu  xmmword ptr [rsp+58h+clsidNew.Data1], xmm0
0x1800770c7  lea     pclsid, [rsp+58h+szProgID]; lplpszProgID
0x1800770cc  lea     paClass, [rsp+58h+clsidNew]; clsid
0x1800770d1  call    cs:__imp_ProgIDFromCLSID
0x1800770d8  nop     dword ptr [rax+rax+00h]
0x1800770dd  mov     edi, eax
0x1800770df  test    eax, eax
0x1800770e1  js      short $exitRtn_15
0x1800770e3  mov     paClass, [rsp+58h+szProgID]; lpString
0x1800770e8  call    cs:__imp_GlobalAddAtomW
0x1800770ef  nop     dword ptr [rax+rax+00h]
0x1800770f4  movups  xmm0, xmmword ptr [rsp+58h+clsidNew.Data1]
0x1800770f9  mov     paClass, [rsp+58h+szProgID]; pv
0x1800770fe  mov     [r14], ax
0x180077102  movdqu  xmmword ptr [rsi], xmm0
0x180077106  call    cs:__imp_CoTaskMemFree
0x18007710d  nop     dword ptr [rax+rax+00h]
0x180077112  mov     eax, edi
0x180077114  mov     paClass, [rsp+58h+var_20]
0x180077119  xor     paClass, rsp; StackCookie
0x18007711c  call    __security_check_cookie
0x180077121  mov     rbx, [rsp+58h+arg_18]
0x180077126  add     rsp, 40h
0x18007712a  pop     r14
0x18007712c  pop     rdi
0x18007712d  pop     rsi
0x18007712e  retn
```
