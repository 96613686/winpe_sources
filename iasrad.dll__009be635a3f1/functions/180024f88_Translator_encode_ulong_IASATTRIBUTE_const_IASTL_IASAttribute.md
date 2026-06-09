# Translator::encode(ulong,_IASATTRIBUTE const &,IASTL::IASAttribute &)

- ea: `0x180024f88`
- end: `0x18002501a`
- name: `?encode@Translator@@KAKKAEBU_IASATTRIBUTE@@AEAVIASAttribute@IASTL@@@Z`
- size: `146`
- prototype: `static unsigned int(unsigned int, const struct _IASATTRIBUTE *, struct IASTL::IASAttribute *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180025840`

## callees

- `0x18001d124`
- `0x180024f88`
- `0x180025020`
- `0x18002569c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024fbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024fbc`

## pseudocode

```c
__int64 __fastcall Translator::encode(unsigned int a1, const struct _IASATTRIBUTE *a2, struct IASTL::IASAttribute *a3)
{
  __int64 v3; // rdi
  unsigned int EncodedSize; // r15d
  unsigned int v7; // ebx
  unsigned __int8 *v8; // rax
  unsigned __int8 *v9; // rsi

  v3 = a1;
  EncodedSize = Translator::getEncodedSize(a2);
  v7 = EncodedSize + v3;
  if ( EncodedSize + (unsigned int)v3 < (unsigned int)v3 )
    _com_issue_error(-2147024362);
  v8 = (unsigned __int8 *)CoTaskMemAlloc(v7);
  v9 = v8;
  if ( !v8 )
    _com_issue_error(-2147024882);
  Translator::encode(&v8[v3], a2);
  *(_DWORD *)(*(_QWORD *)a3 + 8LL) = *((_DWORD *)a2 + 2);
  *(_DWORD *)(*(_QWORD *)a3 + 4LL) = *((_DWORD *)a2 + 1);
  *(_DWORD *)(*(_QWORD *)a3 + 16LL) = 6;
  *(_DWORD *)(*(_QWORD *)a3 + 24LL) = v7;
  *(_QWORD *)(*(_QWORD *)a3 + 32LL) = v9;
  return EncodedSize;
}

```

## disassembly

```asm
0x180024f88  push    rbx
0x180024f8a  push    rbp
0x180024f8b  push    rsi
0x180024f8c  push    rdi
0x180024f8d  push    r14
0x180024f8f  push    r15
0x180024f91  sub     rsp, 28h
0x180024f95  mov     edi, ecx
0x180024f97  mov     r14, r8
0x180024f9a  mov     rcx, rdx; struct _IASATTRIBUTE *
0x180024f9d  mov     rbp, rdx
0x180024fa0  call    ?getEncodedSize@Translator@@KAKAEBU_IASATTRIBUTE@@@Z; Translator::getEncodedSize(_IASATTRIBUTE const &)
0x180024fa5  mov     r15d, eax
0x180024fa8  lea     ebx, [rax+rdi]
0x180024fab  cmp     ebx, edi
0x180024fad  jnb     short loc_180024FBA
0x180024faf  mov     ecx, 80070216h; int
0x180024fb4  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180024fba  mov     ecx, ebx; cb
0x180024fbc  call    cs:__imp_CoTaskMemAlloc
0x180024fc2  mov     rsi, rax
0x180024fc5  test    rax, rax
0x180024fc8  jnz     short loc_180024FD5
0x180024fca  mov     ecx, 8007000Eh; int
0x180024fcf  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180024fd5  lea     rcx, [rax+rdi]; unsigned __int8 *
0x180024fd9  mov     rdx, rbp; struct _IASATTRIBUTE *
0x180024fdc  call    ?encode@Translator@@KAXPEAEAEBU_IASATTRIBUTE@@@Z; Translator::encode(uchar *,_IASATTRIBUTE const &)
0x180024fe1  mov     eax, [rbp+8]
0x180024fe4  mov     rcx, [r14]
0x180024fe7  mov     [rcx+8], eax
0x180024fea  mov     eax, [rbp+4]
0x180024fed  mov     rcx, [r14]
0x180024ff0  mov     [rcx+4], eax
0x180024ff3  mov     rax, [r14]
0x180024ff6  mov     dword ptr [rax+10h], 6
0x180024ffd  mov     rax, [r14]
0x180025000  mov     [rax+18h], ebx
0x180025003  mov     rax, [r14]
0x180025006  mov     [rax+20h], rsi
0x18002500a  mov     eax, r15d
0x18002500d  add     rsp, 28h
0x180025011  pop     r15
0x180025013  pop     r14
0x180025015  pop     rdi
0x180025016  pop     rsi
0x180025017  pop     rbp
0x180025018  pop     rbx
0x180025019  retn
```
