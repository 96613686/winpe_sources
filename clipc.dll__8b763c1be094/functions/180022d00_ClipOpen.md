# ClipOpen

- ea: `0x180022d00`
- end: `0x180022ddc`
- name: `ClipOpen`
- size: `220`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x180006640`
- `0x180006ad0`
- `0x18001003c`
- `0x18001e3f0`
- `0x18001f600`

## callees

- `0x180001140`
- `0x180002b3c`
- `0x1800031ac`
- `0x180022d00`
- `0x180024960`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180022d88`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180022d88`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180022d14`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180022d7e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180022d14`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180022d7e`

## pseudocode

```c
__int64 __fastcall ClipOpen(__int64 a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  LARGE_INTEGER PerformanceCount; // [rsp+30h] [rbp-10h] BYREF
  LONGLONG v9; // [rsp+38h] [rbp-8h] BYREF
  unsigned int v10; // [rsp+58h] [rbp+18h] BYREF
  LARGE_INTEGER v11; // [rsp+60h] [rbp+20h] BYREF
  LARGE_INTEGER Frequency; // [rsp+68h] [rbp+28h] BYREF

  QueryPerformanceCounter(&PerformanceCount);
  v2 = sub_180024960(a1);
  v3 = v2;
  if ( v2 < 0 )
  {
    sub_180002B3C((unsigned int)v2);
    if ( (unsigned int)dword_180030048 > 5
      && (qword_180030058 & 0x400000000000LL) != 0
      && (qword_180030060 & 0x400000000000LL) == qword_180030060 )
    {
      Frequency.QuadPart = 0;
      v11.QuadPart = 0;
      QueryPerformanceCounter(&v11);
      QueryPerformanceFrequency(&Frequency);
      v10 = v3;
      v9 = 1000000 * (v11.QuadPart - PerformanceCount.QuadPart) / Frequency.QuadPart;
      sub_180001140(v4, (unsigned int)word_18002C94A, v5, v6, (__int64)&v10, (__int64)&v9);
    }
  }
  sub_1800031AC(v3);
  return v3;
}

```

## disassembly

```asm
0x180022d00  mov     [rsp-8+arg_0], rbx
0x180022d05  push    rbp
0x180022d06  mov     rbp, rsp
0x180022d09  sub     rsp, 40h
0x180022d0d  mov     rbx, rcx
0x180022d10  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180022d14  call    cs:QueryPerformanceCounter
0x180022d1a  mov     rcx, rbx
0x180022d1d  call    sub_180024960
0x180022d22  mov     ebx, eax
0x180022d24  test    eax, eax
0x180022d26  jns     loc_180022DC8
0x180022d2c  mov     ecx, eax
0x180022d2e  call    sub_180002B3C
0x180022d33  mov     ecx, cs:dword_180030048
0x180022d39  cmp     ecx, 5
0x180022d3c  jbe     loc_180022DC8
0x180022d42  mov     rdx, cs:qword_180030060
0x180022d49  mov     r8, 400000000000h
0x180022d53  mov     rcx, cs:qword_180030058
0x180022d5a  test    r8, rcx
0x180022d5d  jz      short loc_180022DC8
0x180022d5f  mov     rax, rdx
0x180022d62  and     rax, r8
0x180022d65  cmp     rax, rdx
0x180022d68  jnz     short loc_180022DC8
0x180022d6a  lea     rcx, [rbp+arg_10]; lpPerformanceCount
0x180022d6e  mov     qword ptr [rbp+Frequency], 0
0x180022d76  mov     qword ptr [rbp+arg_10], 0
0x180022d7e  call    cs:QueryPerformanceCounter
0x180022d84  lea     rcx, [rbp+Frequency]; lpFrequency
0x180022d88  call    cs:QueryPerformanceFrequency
0x180022d8e  mov     rax, qword ptr [rbp+arg_10]
0x180022d92  sub     rax, qword ptr [rbp+PerformanceCount]
0x180022d96  imul    rax, 0F4240h
0x180022d9d  mov     [rbp+arg_8], ebx
0x180022da0  cqo
0x180022da2  idiv    qword ptr [rbp+Frequency]
0x180022da6  lea     rdx, word_18002C94A
0x180022dad  mov     [rbp+var_8], rax
0x180022db1  lea     rax, [rbp+var_8]
0x180022db5  mov     [rsp+40h+var_18], rax
0x180022dba  lea     rax, [rbp+arg_8]
0x180022dbe  mov     [rsp+40h+var_20], rax
0x180022dc3  call    sub_180001140
0x180022dc8  mov     ecx, ebx
0x180022dca  call    sub_1800031AC
0x180022dcf  mov     eax, ebx
0x180022dd1  mov     rbx, [rsp+40h+arg_0]
0x180022dd6  add     rsp, 40h
0x180022dda  pop     rbp
0x180022ddb  retn
```
