# NgcUtils::SetNCryptBoolProperty(unsigned __int64,ushort const *,int)

- ea: `0x1800148b4`
- end: `0x180014910`
- name: `?SetNCryptBoolProperty@NgcUtils@@YAJ_KPEBGH@Z`
- size: `92`
- prototype: `__int64 __fastcall(NgcUtils *__hidden this, unsigned __int64, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001b0b4`

## callees

- `0x18000b0fc`
- `0x1800148b4`

## import_xrefs

- `ncrypt!NCryptSetProperty` at `0x1800148df`
- `ncrypt!NCryptSetProperty` at `0x1800148df`

## string_xrefs

- `0x1800148f0`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcUtils::SetNCryptBoolProperty(NgcUtils *this, __int64 a2, const unsigned __int16 *a3)
{
  SECURITY_STATUS v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v8; // [rsp+50h] [rbp+18h] BYREF

  v8 = 1;
  v3 = NCryptSetProperty((NCRYPT_HANDLE)this, L"PCP_NO_DA_PROTECTION", (PBYTE)&v8, 4u, 0);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x173,
    (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
    (const char *)(unsigned int)v3,
    v6);
  return v4;
}

```

## disassembly

```asm
0x1800148b4  mov     rax, rsp
0x1800148b7  mov     [rax+18h], r8d
0x1800148bb  push    rbx
0x1800148bc  sub     rsp, 30h
0x1800148c0  mov     r9d, 4; cbInput
0x1800148c6  mov     dword ptr [rax+18h], 1
0x1800148cd  lea     r8, [rax+18h]; pbInput
0x1800148d1  mov     dword ptr [rax-18h], 0
0x1800148d8  lea     rdx, aPcpNoDaProtect; "PCP_NO_DA_PROTECTION"
0x1800148df  call    cs:__imp_NCryptSetProperty
0x1800148e5  mov     ebx, eax
0x1800148e7  test    eax, eax
0x1800148e9  jns     short loc_180014908
0x1800148eb  mov     rcx, [rsp+38h]; this
0x1800148f0  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800148f7  mov     r9d, eax; char *
0x1800148fa  mov     edx, 173h; void *
0x1800148ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014904  mov     eax, ebx
0x180014906  jmp     short loc_18001490A
0x180014908  xor     eax, eax
0x18001490a  add     rsp, 30h
0x18001490e  pop     rbx
0x18001490f  retn
```
