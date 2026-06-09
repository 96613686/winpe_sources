# DecodingThreadProc(void *)

- ea: `0x18001fa90`
- end: `0x18001fae9`
- name: `?DecodingThreadProc@@YAKPEAX@Z`
- size: `89`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001f978`
- `0x18001fa90`

## import_xrefs

- `AVRT!AvRevertMmThreadCharacteristics` at `0x18001fad1`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x18001fad1`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x18001fab6`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x18001fab6`

## pseudocode

```c
__int64 __fastcall DecodingThreadProc(DWORD *lpThreadParameter)
{
  const WCHAR *v2; // rcx
  HANDLE v3; // rbx
  unsigned int v4; // edi

  v2 = (const WCHAR *)(lpThreadParameter + 4);
  v3 = 0;
  if ( *v2 )
    v3 = AvSetMmThreadCharacteristicsW(v2, lpThreadParameter + 132);
  v4 = CFLACDecoder::DecodingThread((CFLACDecoder *)lpThreadParameter);
  if ( v3 )
    AvRevertMmThreadCharacteristics(v3);
  return v4;
}

```

## disassembly

```asm
0x18001fa90  mov     [rsp+arg_0], rbx
0x18001fa95  mov     [rsp+arg_8], rsi
0x18001fa9a  push    rdi
0x18001fa9b  sub     rsp, 20h
0x18001fa9f  xor     esi, esi
0x18001faa1  mov     rdi, rcx
0x18001faa4  add     rcx, 10h; TaskName
0x18001faa8  mov     ebx, esi
0x18001faaa  cmp     [rcx], si
0x18001faad  jz      short loc_18001FABF
0x18001faaf  lea     rdx, [rdi+210h]; TaskIndex
0x18001fab6  call    cs:__imp_AvSetMmThreadCharacteristicsW
0x18001fabc  mov     rbx, rax
0x18001fabf  mov     rcx, rdi; this
0x18001fac2  call    ?DecodingThread@CFLACDecoder@@QEAAJXZ; CFLACDecoder::DecodingThread(void)
0x18001fac7  mov     edi, eax
0x18001fac9  test    rbx, rbx
0x18001facc  jz      short loc_18001FAD7
0x18001face  mov     rcx, rbx; AvrtHandle
0x18001fad1  call    cs:__imp_AvRevertMmThreadCharacteristics
0x18001fad7  mov     rbx, [rsp+28h+arg_0]
0x18001fadc  mov     eax, edi
0x18001fade  mov     rsi, [rsp+28h+arg_8]
0x18001fae3  add     rsp, 20h
0x18001fae7  pop     rdi
0x18001fae8  retn
```
