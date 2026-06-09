# ClipClose

- ea: `0x18001ea20`
- end: `0x18001eafc`
- name: `ClipClose`
- size: `220`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x18000414c`
- `0x180006640`
- `0x180006ad0`
- `0x18001e3f0`
- `0x18001f600`

## callees

- `0x180001140`
- `0x180002b3c`
- `0x1800031ac`
- `0x18001ea20`
- `0x180024604`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18001eaa8`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18001eaa8`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001ea34`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001ea9e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001ea34`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001ea9e`

## pseudocode

```c
__int64 __fastcall ClipClose(__int64 a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  LARGE_INTEGER PerformanceCount; // [rsp+30h] [rbp-10h] BYREF
  LONGLONG v9; // [rsp+38h] [rbp-8h] BYREF
  unsigned int v10; // [rsp+58h] [rbp+18h] BYREF
  LARGE_INTEGER v11; // [rsp+60h] [rbp+20h] BYREF
  LARGE_INTEGER Frequency; // [rsp+68h] [rbp+28h] BYREF

  QueryPerformanceCounter(&PerformanceCount);
  v2 = sub_180024604(a1);
  v3 = v2;
  if ( v2 < 0 )
  {
    sub_180002B3C(v2);
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
      sub_180001140(v4, (unsigned __int8 *)&dword_18002C924, v5, v6, (__int64)&v10, (__int64)&v9);
    }
  }
  sub_1800031AC(v3);
  return v3;
}

```

## disassembly

```asm
0x18001ea20  mov     [rsp-8+arg_0], rbx
0x18001ea25  push    rbp
0x18001ea26  mov     rbp, rsp
0x18001ea29  sub     rsp, 40h
0x18001ea2d  mov     rbx, rcx
0x18001ea30  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18001ea34  call    cs:QueryPerformanceCounter
0x18001ea3a  mov     rcx, rbx
0x18001ea3d  call    sub_180024604
0x18001ea42  mov     ebx, eax
0x18001ea44  test    eax, eax
0x18001ea46  jns     loc_18001EAE8
0x18001ea4c  mov     ecx, eax
0x18001ea4e  call    sub_180002B3C
0x18001ea53  mov     ecx, cs:dword_180030048
0x18001ea59  cmp     ecx, 5
0x18001ea5c  jbe     loc_18001EAE8
0x18001ea62  mov     rdx, cs:qword_180030060
0x18001ea69  mov     r8, 400000000000h
0x18001ea73  mov     rcx, cs:qword_180030058
0x18001ea7a  test    r8, rcx
0x18001ea7d  jz      short loc_18001EAE8
0x18001ea7f  mov     rax, rdx
0x18001ea82  and     rax, r8
0x18001ea85  cmp     rax, rdx
0x18001ea88  jnz     short loc_18001EAE8
0x18001ea8a  lea     rcx, [rbp+arg_10]; lpPerformanceCount
0x18001ea8e  mov     qword ptr [rbp+Frequency], 0
0x18001ea96  mov     qword ptr [rbp+arg_10], 0
0x18001ea9e  call    cs:QueryPerformanceCounter
0x18001eaa4  lea     rcx, [rbp+Frequency]; lpFrequency
0x18001eaa8  call    cs:QueryPerformanceFrequency
0x18001eaae  mov     rax, qword ptr [rbp+arg_10]
0x18001eab2  sub     rax, qword ptr [rbp+PerformanceCount]
0x18001eab6  imul    rax, 0F4240h
0x18001eabd  mov     [rbp+arg_8], ebx
0x18001eac0  cqo
0x18001eac2  idiv    qword ptr [rbp+Frequency]
0x18001eac6  lea     rdx, dword_18002C924
0x18001eacd  mov     [rbp+var_8], rax
0x18001ead1  lea     rax, [rbp+var_8]
0x18001ead5  mov     [rsp+40h+var_18], rax
0x18001eada  lea     rax, [rbp+arg_8]
0x18001eade  mov     [rsp+40h+var_20], rax
0x18001eae3  call    sub_180001140
0x18001eae8  mov     ecx, ebx
0x18001eaea  call    sub_1800031AC
0x18001eaef  mov     eax, ebx
0x18001eaf1  mov     rbx, [rsp+40h+arg_0]
0x18001eaf6  add     rsp, 40h
0x18001eafa  pop     rbp
0x18001eafb  retn
```
