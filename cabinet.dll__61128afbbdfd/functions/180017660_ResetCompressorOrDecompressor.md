# ResetCompressorOrDecompressor

- ea: `0x180017660`
- end: `0x1800176bc`
- name: `ResetCompressorOrDecompressor`
- size: `92`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180017650`
- `0x1800176d0`

## callees

- `0x180011d6c`
- `0x180017660`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800176af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800176af`

## pseudocode

```c
__int64 __fastcall ResetCompressorOrDecompressor(__int64 a1, __int64 a2)
{
  DWORD v2; // eax
  int *v3; // rcx
  int v4; // eax
  __int64 v5; // rcx
  __int64 *v6; // rdx

  v2 = CmpsValidateHandle(a1, a2);
  if ( !v2 )
  {
    v4 = *v3;
    v5 = *((_QWORD *)v3 + 1);
    v6 = &qword_18001D148;
    if ( (v4 & 0x40000000) == 0 )
      v6 = &qword_18001D028;
    v2 = ((__int64 (__fastcall *)(__int64))v6[6 * (v4 & 0x9FFFFFFF)])(v5);
    if ( !v2 )
      return 1;
  }
  SetLastError(v2);
  return 0;
}

```

## disassembly

```asm
0x180017660  sub     rsp, 28h
0x180017664  call    CmpsValidateHandle
0x180017669  test    eax, eax
0x18001766b  jnz     short loc_1800176AD
0x18001766d  mov     eax, [rcx]
0x18001766f  lea     r8, qword_18001D028
0x180017676  mov     rcx, [rcx+8]
0x18001767a  lea     rdx, qword_18001D148
0x180017681  bt      eax, 1Eh
0x180017685  cmovnb  rdx, r8
0x180017689  mov     r8d, 9FFFFFFFh
0x18001768f  and     rax, r8
0x180017692  lea     rax, [rax+rax*2]
0x180017696  add     rax, rax
0x180017699  mov     rax, [rdx+rax*8]
0x18001769d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800176a2  test    eax, eax
0x1800176a4  jnz     short loc_1800176AD
0x1800176a6  mov     eax, 1
0x1800176ab  jmp     short loc_1800176B7
0x1800176ad  mov     ecx, eax; dwErrCode
0x1800176af  call    cs:__imp_SetLastError
0x1800176b5  xor     eax, eax
0x1800176b7  add     rsp, 28h
0x1800176bb  retn
```
