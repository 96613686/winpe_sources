# BackgroundCopyJobNotify::QueryInterface(_GUID const &,void * *)

- ea: `0x180012c00`
- end: `0x180012c8d`
- name: `?QueryInterface@BackgroundCopyJobNotify@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `141`
- prototype: `int __fastcall(BackgroundCopyJobNotify *this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180012c00`

## import_xrefs

- `ZTrace_Maps!ZTraceReportOrigination` at `0x180012c1a`

## string_xrefs

- `0x180012c08`: `BackgroundCopyJobNotify::QueryInterface`

## pseudocode

```c
int __fastcall BackgroundCopyJobNotify::QueryInterface(
        BackgroundCopyJobNotify *this,
        const struct _GUID *a2,
        void **a3)
{
  int result; // eax
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax

  if ( !a3 )
    return ZTraceReportOrigination(-2147467261, "BackgroundCopyJobNotify::QueryInterface", 32, this);
  *a3 = 0;
  v4 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data1 )
    v4 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4;
  if ( v4 )
  {
    v5 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_97ea99c7_0186_4ad4_8df9_c5b4e0ed6b22.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_97ea99c7_0186_4ad4_8df9_c5b4e0ed6b22.Data1 )
      v5 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_97ea99c7_0186_4ad4_8df9_c5b4e0ed6b22.Data4;
    if ( v5 )
    {
      v6 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_659cdeac_489e_11d9_a9cd_000d56965251.Data1;
      if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_659cdeac_489e_11d9_a9cd_000d56965251.Data1 )
        v6 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_659cdeac_489e_11d9_a9cd_000d56965251.Data4;
      if ( v6 )
        return -2147467262;
    }
  }
  result = 0;
  *a3 = this;
  _InterlockedIncrement((volatile signed __int32 *)this + 6);
  return result;
}

```

## disassembly

```asm
0x180012c00  test    r8, r8
0x180012c03  jnz     short loc_180012C21
0x180012c05  mov     r9, rcx
0x180012c08  lea     rdx, aBackgroundcopy_5; "BackgroundCopyJobNotify::QueryInterface"
0x180012c0f  mov     ecx, 80004003h
0x180012c14  mov     r8d, 20h ; ' '
0x180012c1a  jmp     cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x180012c21  mov     qword ptr [r8], 0
0x180012c28  mov     rax, [rdx]
0x180012c2b  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data1
0x180012c32  jnz     short loc_180012C3F
0x180012c34  mov     rax, [rdx+8]
0x180012c38  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x180012c3f  test    rax, rax
0x180012c42  jz      short loc_180012C83
0x180012c44  mov     rax, [rdx]
0x180012c47  sub     rax, qword ptr cs:_GUID_97ea99c7_0186_4ad4_8df9_c5b4e0ed6b22.Data1
0x180012c4e  jnz     short loc_180012C5B
0x180012c50  mov     rax, [rdx+8]
0x180012c54  sub     rax, qword ptr cs:_GUID_97ea99c7_0186_4ad4_8df9_c5b4e0ed6b22.Data4
0x180012c5b  test    rax, rax
0x180012c5e  jz      short loc_180012C83
0x180012c60  mov     rax, [rdx]
0x180012c63  sub     rax, qword ptr cs:_GUID_659cdeac_489e_11d9_a9cd_000d56965251.Data1
0x180012c6a  jnz     short loc_180012C77
0x180012c6c  mov     rax, [rdx+8]
0x180012c70  sub     rax, qword ptr cs:_GUID_659cdeac_489e_11d9_a9cd_000d56965251.Data4
0x180012c77  test    rax, rax
0x180012c7a  jz      short loc_180012C83
0x180012c7c  mov     eax, 80004002h
0x180012c81  jmp     short locret_180012C8C
0x180012c83  xor     eax, eax
0x180012c85  mov     [r8], rcx
0x180012c88  lock inc dword ptr [rcx+18h]
0x180012c8c  retn
```
