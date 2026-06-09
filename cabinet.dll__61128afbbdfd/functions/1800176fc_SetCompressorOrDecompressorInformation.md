# SetCompressorOrDecompressorInformation

- ea: `0x1800176fc`
- end: `0x180017770`
- name: `SetCompressorOrDecompressorInformation`
- size: `116`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800176e0`
- `0x180017780`

## callees

- `0x180011d6c`
- `0x1800176fc`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017763`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017763`

## pseudocode

```c
__int64 __fastcall SetCompressorOrDecompressorInformation(
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
      v12 = &qword_18001D130;
      if ( (v10 & 0x40000000) == 0 )
        v12 = &qword_18001D010;
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
0x1800176fc  sub     rsp, 38h
0x180017700  mov     r11d, edx
0x180017703  mov     edx, [rsp+38h+arg_20]
0x180017707  call    CmpsValidateHandle
0x18001770c  test    eax, eax
0x18001770e  jnz     short loc_180017761
0x180017710  test    r8, r8
0x180017713  jz      short loc_18001775C
0x180017715  test    r9, r9
0x180017718  jz      short loc_18001775C
0x18001771a  mov     eax, [rcx]
0x18001771c  lea     rdx, qword_18001D010
0x180017723  mov     rcx, [rcx+8]
0x180017727  lea     r10, qword_18001D130
0x18001772e  bt      eax, 1Eh
0x180017732  cmovnb  r10, rdx
0x180017736  mov     edx, 9FFFFFFFh
0x18001773b  and     rax, rdx
0x18001773e  mov     edx, r11d
0x180017741  lea     rax, [rax+rax*2]
0x180017745  add     rax, rax
0x180017748  mov     rax, [r10+rax*8]
0x18001774c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017751  test    eax, eax
0x180017753  jnz     short loc_180017761
0x180017755  mov     eax, 1
0x18001775a  jmp     short loc_18001776B
0x18001775c  mov     eax, 57h ; 'W'
0x180017761  mov     ecx, eax; dwErrCode
0x180017763  call    cs:__imp_SetLastError
0x180017769  xor     eax, eax
0x18001776b  add     rsp, 38h
0x18001776f  retn
```
