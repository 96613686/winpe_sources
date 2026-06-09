# CHostObj::ConnectObject(IDispatch *,ushort *)

- ea: `0x140012050`
- end: `0x1400120a6`
- name: `?ConnectObject@CHostObj@@UEAAJPEAUIDispatch@@PEAG@Z`
- size: `86`
- prototype: `int(CHostObj *__hidden this, struct IDispatch *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x14000d2e0`
- `0x140011d54`
- `0x140012050`

## string_xrefs

- `0x14001207e`: `WScript.CreateObject`

## pseudocode

```c
__int64 __fastcall CHostObj::ConnectObject(CHostObj *this, struct IDispatch *a2, unsigned __int16 *a3)
{
  if ( !a2 || !a3 || !*a3 )
    return 2147942487LL;
  if ( (int)ConnectObject_0(a2) >= 0 )
    return 0;
  Signal_Exception(&IID_IHost, L"WScript.CreateObject", 0xC1Eu);
  return 2147614729LL;
}

```

## disassembly

```asm
0x140012050  sub     rsp, 28h
0x140012054  mov     r9, rdx
0x140012057  test    rdx, rdx
0x14001205a  jz      short loc_14001209C
0x14001205c  test    r8, r8
0x14001205f  jz      short loc_14001209C
0x140012061  xor     eax, eax
0x140012063  cmp     ax, [r8]
0x140012067  jz      short loc_14001209C
0x140012069  mov     rdx, r8
0x14001206c  mov     rcx, r9; struct IDispatch *
0x14001206f  call    ConnectObject_0
0x140012074  test    eax, eax
0x140012076  jns     short loc_140012098
0x140012078  mov     r8d, 0C1Eh; unsigned int
0x14001207e  lea     rdx, aWscriptCreateo; "WScript.CreateObject"
0x140012085  lea     rcx, IID_IHost; struct _GUID *
0x14001208c  call    ?Signal_Exception@@YAJAEBU_GUID@@PEBGIZZ; Signal_Exception(_GUID const &,ushort const *,uint,...)
0x140012091  mov     eax, 80020009h
0x140012096  jmp     short loc_1400120A1
0x140012098  xor     eax, eax
0x14001209a  jmp     short loc_1400120A1
0x14001209c  mov     eax, 80070057h
0x1400120a1  add     rsp, 28h
0x1400120a5  retn
```
