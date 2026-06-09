# IASStoreAccountSID(IAttributesRaw *,ulong,void *)

- ea: `0x180016938`
- end: `0x1800169d9`
- name: `?IASStoreAccountSID@@YAJPEAUIAttributesRaw@@KPEAX@Z`
- size: `161`
- prototype: `__int64 __fastcall(struct IAttributesRaw *, unsigned int, void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000d794`
- `0x18000f890`

## callees

- `0x18000acf4`
- `0x18000bea8`
- `0x18000c28c`
- `0x18000d55c`
- `0x180016938`

## import_xrefs

- `ADVAPI32!GetLengthSid` at `0x180016960`
- `ADVAPI32!GetLengthSid` at `0x180016960`
- `ADVAPI32!IsValidSid` at `0x180016953`
- `ADVAPI32!IsValidSid` at `0x180016953`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IASStoreAccountSID(struct IAttributesRaw *a1, int a2, void *a3)
{
  DWORD LengthSid; // eax
  bool v7; // dl
  DWORD v8; // edi
  __int64 result; // rax
  int v10; // ecx
  const _com_error *v11; // [rsp+20h] [rbp-38h] BYREF
  LPVOID pv; // [rsp+70h] [rbp+18h] BYREF

  if ( !a3 )
    return 2147942487LL;
  if ( !IsValidSid(a3) )
    return 2147942487LL;
  LengthSid = GetLengthSid(a3);
  v8 = LengthSid;
  if ( !LengthSid )
    return 2147942487LL;
  try
  {
    IASTL::IASAttribute::IASAttribute((IASTL::IASAttribute *)&pv, v7);
    *((_DWORD *)pv + 2) = a2;
    *((_DWORD *)pv + 4) = 6;
    IASTL::IASAttribute::setOctetString((IASTL::IASAttribute *)&pv, v8, (const unsigned __int8 *)a3);
    IASTL::IASAttribute::store((IASTL::IASAttribute *)&pv, a1);
    if ( pv )
      IASAttributeRelease(pv);
    result = 0;
  }
  catch ( const _com_error *v11 )
  {
    v10 = *((_DWORD *)v11 + 2);
    if ( v10 > 0 )
      LODWORD(pv) = (unsigned __int16)v10 | 0x80070000;
    else
      LODWORD(pv) = *((_DWORD *)v11 + 2);
    return (unsigned int)pv;
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x180016938  push    rbx
0x18001693a  push    rsi
0x18001693b  push    rdi
0x18001693c  push    r14
0x18001693e  sub     rsp, 38h
0x180016942  mov     rbx, r8
0x180016945  mov     r14d, edx
0x180016948  mov     rsi, rcx
0x18001694b  test    r8, r8
0x18001694e  jz      short loc_1800169CA
0x180016950  mov     rcx, rbx; pSid
0x180016953  call    cs:__imp_IsValidSid
0x180016959  test    eax, eax
0x18001695b  jz      short loc_1800169CA
0x18001695d  mov     rcx, rbx; pSid
0x180016960  call    cs:__imp_GetLengthSid
0x180016966  mov     edi, eax
0x180016968  test    eax, eax
0x18001696a  jz      short loc_1800169CA
0x18001696c  lea     rcx, [rsp+58h+pv]; this
0x180016971  call    ??0IASAttribute@IASTL@@QEAA@_N@Z; IASTL::IASAttribute::IASAttribute(bool)
0x180016976  nop
0x180016977  mov     rcx, [rsp+58h+pv]
0x18001697c  mov     [rcx+8], r14d
0x180016980  mov     rax, [rsp+58h+pv]
0x180016985  mov     dword ptr [rax+10h], 6
0x18001698c  mov     r8, rbx; Src
0x18001698f  mov     edx, edi; Size
0x180016991  lea     rcx, [rsp+58h+pv]; this
0x180016996  call    ?setOctetString@IASAttribute@IASTL@@QEAAXKPEBE@Z; IASTL::IASAttribute::setOctetString(ulong,uchar const *)
0x18001699b  mov     rdx, rsi; struct IAttributesRaw *
0x18001699e  lea     rcx, [rsp+58h+pv]; this
0x1800169a3  call    ?store@IASAttribute@IASTL@@QEBAXPEAUIAttributesRaw@@@Z; IASTL::IASAttribute::store(IAttributesRaw *)
0x1800169a8  nop
0x1800169a9  mov     rcx, [rsp+58h+pv]; pv
0x1800169ae  test    rcx, rcx
0x1800169b1  jz      short loc_1800169B9
0x1800169b3  call    IASAttributeRelease
0x1800169b8  nop
0x1800169b9  xor     eax, eax
0x1800169bb  jmp     short loc_1800169CF
0x1800169bd  mov     eax, dword ptr [rsp+58h+pv]
0x1800169c1  jmp     short loc_1800169CF
0x1800169c3  mov     eax, 8007000Eh
0x1800169c8  jmp     short loc_1800169CF
0x1800169ca  mov     eax, 80070057h
0x1800169cf  add     rsp, 38h
0x1800169d3  pop     r14
0x1800169d5  pop     rdi
0x1800169d6  pop     rsi
0x1800169d7  pop     rbx
0x1800169d8  retn
```
