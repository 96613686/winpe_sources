# QueryCompressorOrDecompressorInformation

- ea: `0x1800175ac`
- end: `0x180017620`
- name: `QueryCompressorOrDecompressorInformation`
- size: `116`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180017590`
- `0x180017630`

## callees

- `0x180011d6c`
- `0x1800175ac`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017613`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017613`

## pseudocode

```c
__int64 __fastcall QueryCompressorOrDecompressorInformation(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5)
{
  DWORD v5; // eax
  int *v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  unsigned int v9; // r11d
  int v10; // eax
  __int64 v11; // rcx
  __int64 *v12; // r10

  v5 = CmpsValidateHandle(a1, a5);
  if ( !v5 )
  {
    if ( v7 && v8 )
    {
      v10 = *v6;
      v11 = *((_QWORD *)v6 + 1);
      v12 = &qword_18001D138;
      if ( (v10 & 0x40000000) == 0 )
        v12 = &qword_18001D018;
      v5 = ((__int64 (__fastcall *)(__int64, _QWORD))v12[6 * (v10 & 0x9FFFFFFF)])(v11, v9);
      if ( !v5 )
        return 1;
    }
    else
    {
      v5 = 87;
    }
  }
  SetLastError(v5);
  return 0;
}

```

## disassembly

```asm
0x1800175ac  sub     rsp, 38h
0x1800175b0  mov     r11d, edx
0x1800175b3  mov     edx, [rsp+38h+arg_20]
0x1800175b7  call    CmpsValidateHandle
0x1800175bc  test    eax, eax
0x1800175be  jnz     short loc_180017611
0x1800175c0  test    r8, r8
0x1800175c3  jz      short loc_18001760C
0x1800175c5  test    r9, r9
0x1800175c8  jz      short loc_18001760C
0x1800175ca  mov     eax, [rcx]
0x1800175cc  lea     rdx, qword_18001D018
0x1800175d3  mov     rcx, [rcx+8]
0x1800175d7  lea     r10, qword_18001D138
0x1800175de  bt      eax, 1Eh
0x1800175e2  cmovnb  r10, rdx
0x1800175e6  mov     edx, 9FFFFFFFh
0x1800175eb  and     rax, rdx
0x1800175ee  mov     edx, r11d
0x1800175f1  lea     rax, [rax+rax*2]
0x1800175f5  add     rax, rax
0x1800175f8  mov     rax, [r10+rax*8]
0x1800175fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017601  test    eax, eax
0x180017603  jnz     short loc_180017611
0x180017605  mov     eax, 1
0x18001760a  jmp     short loc_18001761B
0x18001760c  mov     eax, 57h ; 'W'
0x180017611  mov     ecx, eax; dwErrCode
0x180017613  call    cs:__imp_SetLastError
0x180017619  xor     eax, eax
0x18001761b  add     rsp, 38h
0x18001761f  retn
```
