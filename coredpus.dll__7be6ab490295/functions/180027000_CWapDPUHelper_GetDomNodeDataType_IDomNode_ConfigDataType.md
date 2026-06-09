# CWapDPUHelper::GetDomNodeDataType(IDomNode *,ConfigDataType *)

- ea: `0x180027000`
- end: `0x1800270a6`
- name: `?GetDomNodeDataType@CWapDPUHelper@@UEAAJPEAUIDomNode@@PEAW4ConfigDataType@@@Z`
- size: `166`
- prototype: `__int64 __fastcall(CWapDPUHelper *__hidden this, struct IDomNode *, enum ConfigDataType *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180027000`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18002707d`
- `OLEAUT32!__imp_SysFreeString` at `0x18002708c`
- `OLEAUT32!__imp_SysFreeString` at `0x18002707d`
- `OLEAUT32!__imp_SysFreeString` at `0x18002708c`
- `DMCfgUtils!CfgUtilParseConfigDataTypeName` at `0x18002706a`
- `DMCfgUtils!CfgUtilParseConfigDataTypeName` at `0x18002706a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWapDPUHelper::GetDomNodeDataType(CWapDPUHelper *this, struct IDomNode *a2, enum ConfigDataType *a3)
{
  unsigned int v4; // ebx
  BSTR bstrString; // [rsp+38h] [rbp+10h] BYREF
  __int64 v7; // [rsp+40h] [rbp+18h]

  v7 = 0;
  bstrString = 0;
  *(_DWORD *)a3 = 10;
  v4 = (*(__int64 (__fastcall **)(struct IDomNode *, const wchar_t *, BSTR *))(*(_QWORD *)a2 + 88LL))(
         a2,
         L"datatype",
         &bstrString);
  if ( (int)(v4 + 0x80000000) < 0 || v4 == -2147023728 )
  {
    if ( v4 == -2147023728 )
    {
      *(_DWORD *)a3 = 1;
      v4 = 0;
    }
    else
    {
      *(_DWORD *)a3 = CfgUtilParseConfigDataTypeName(bstrString, 2147943568LL);
    }
  }
  SysFreeString(bstrString);
  SysFreeString(0);
  return v4;
}

```

## disassembly

```asm
0x180027000  mov     r11, rsp
0x180027003  mov     [r11+8], rbx
0x180027007  push    rdi
0x180027008  sub     rsp, 20h
0x18002700c  mov     rdi, r8
0x18002700f  mov     rcx, rdx
0x180027012  mov     qword ptr [r11+18h], 0
0x18002701a  mov     qword ptr [r11+10h], 0
0x180027022  mov     dword ptr [r8], 0Ah
0x180027029  mov     rax, [rdx]
0x18002702c  lea     r8, [r11+10h]
0x180027030  lea     rdx, aDatatype; "datatype"
0x180027037  mov     rax, [rax+58h]
0x18002703b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027040  mov     ebx, eax
0x180027042  mov     eax, 80000000h
0x180027047  lea     ecx, [rbx+rax]
0x18002704a  mov     edx, 80070490h
0x18002704f  test    eax, ecx
0x180027051  jnz     short loc_180027057
0x180027053  cmp     ebx, edx
0x180027055  jnz     short loc_180027078
0x180027057  cmp     ebx, edx
0x180027059  jnz     short loc_180027065
0x18002705b  mov     dword ptr [rdi], 1
0x180027061  xor     ebx, ebx
0x180027063  jmp     short loc_180027078
0x180027065  mov     rcx, [rsp+28h+bstrString]
0x18002706a  call    cs:__imp_CfgUtilParseConfigDataTypeName
0x180027071  nop     dword ptr [rax+rax+00h]
0x180027076  mov     [rdi], eax
0x180027078  mov     rcx, [rsp+28h+bstrString]; bstrString
0x18002707d  call    cs:__imp_SysFreeString
0x180027084  nop     dword ptr [rax+rax+00h]
0x180027089  nop
0x18002708a  xor     ecx, ecx; bstrString
0x18002708c  call    cs:__imp_SysFreeString
0x180027093  nop     dword ptr [rax+rax+00h]
0x180027098  mov     eax, ebx
0x18002709a  mov     rbx, [rsp+28h+arg_0]
0x18002709f  add     rsp, 20h
0x1800270a3  pop     rdi
0x1800270a4  retn
```
