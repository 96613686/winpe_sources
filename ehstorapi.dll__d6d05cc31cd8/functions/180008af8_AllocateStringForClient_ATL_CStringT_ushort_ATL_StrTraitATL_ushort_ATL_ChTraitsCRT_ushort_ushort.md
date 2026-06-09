# AllocateStringForClient(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,ushort * *)

- ea: `0x180008af8`
- end: `0x180008b8a`
- name: `?AllocateStringForClient@@YAJPEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAG@Z`
- size: `146`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180002bf0`
- `0x1800089d0`
- `0x1800089f0`

## callees

- `0x180003ce0`
- `0x180008af8`
- `0x18000c4b6`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008b58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008b58`

## pseudocode

```c
__int64 __fastcall AllocateStringForClient(const void **a1, _QWORD *a2)
{
  __int64 result; // rax
  SIZE_T v5; // rdi
  void *v6; // rax
  void *v7; // rsi

  if ( a2 )
  {
    v5 = 2LL * (*((_DWORD *)*a1 - 4) + 1);
    v6 = CoTaskMemAlloc(v5);
    v7 = v6;
    if ( v6 )
    {
      memcpy_0(v6, *a1, v5);
      result = 0;
      *a2 = v7;
    }
    else
    {
      return 2147942414LL;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_0c4586013be53aed3cf38dadc6a40be3_Traceguids,
        "ppwszString != NULL");
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x180008af8  push    rbx
0x180008afa  push    rsi
0x180008afb  push    rdi
0x180008afc  push    r14
0x180008afe  sub     rsp, 28h
0x180008b02  mov     rbx, rdx
0x180008b05  mov     r14, rcx
0x180008b08  test    rdx, rdx
0x180008b0b  jnz     short loc_180008B47
0x180008b0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008b14  lea     rax, WPP_GLOBAL_Control
0x180008b1b  cmp     rcx, rax
0x180008b1e  jz      short loc_180008B40
0x180008b20  test    byte ptr [rcx+1Ch], 2
0x180008b24  jz      short loc_180008B40
0x180008b26  mov     rcx, [rcx+10h]
0x180008b2a  lea     edx, [rbx+0Ah]
0x180008b2d  lea     r9, aPpwszstringNul; "ppwszString != NULL"
0x180008b34  lea     r8, WPP_0c4586013be53aed3cf38dadc6a40be3_Traceguids
0x180008b3b  call    WPP_SF_s
0x180008b40  mov     eax, 80070057h
0x180008b45  jmp     short loc_180008B80
0x180008b47  mov     rax, [rcx]
0x180008b4a  mov     ecx, [rax-10h]
0x180008b4d  inc     ecx
0x180008b4f  movsxd  rdi, ecx
0x180008b52  add     rdi, rdi
0x180008b55  mov     rcx, rdi; cb
0x180008b58  call    cs:__imp_CoTaskMemAlloc
0x180008b5e  mov     rsi, rax
0x180008b61  test    rax, rax
0x180008b64  jnz     short loc_180008B6D
0x180008b66  mov     eax, 8007000Eh
0x180008b6b  jmp     short loc_180008B80
0x180008b6d  mov     rdx, [r14]; Src
0x180008b70  mov     r8, rdi; Size
0x180008b73  mov     rcx, rsi; void *
0x180008b76  call    memcpy_0
0x180008b7b  xor     eax, eax
0x180008b7d  mov     [rbx], rsi
0x180008b80  add     rsp, 28h
0x180008b84  pop     r14
0x180008b86  pop     rdi
0x180008b87  pop     rsi
0x180008b88  pop     rbx
0x180008b89  retn
```
