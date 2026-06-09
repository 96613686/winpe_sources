# ClipGatherDiagnostics

- ea: `0x18001eb10`
- end: `0x18001ed33`
- name: `ClipGatherDiagnostics`
- size: `547`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, LARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x180001140`
- `0x180002b3c`
- `0x1800031ac`
- `0x180006390`
- `0x18001b434`
- `0x18001b8c4`
- `0x18001dfd0`
- `0x18001eb10`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ecda`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ecda`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ece9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ece9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ecfe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ecfe`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18001ec84`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18001ec84`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001eb57`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001ec7a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001eb57`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001ec7a`

## string_xrefs

- `0x18001eba6`: `DiagXml`

## pseudocode

```c
__int64 __fastcall ClipGatherDiagnostics(__int64 a1, const WCHAR *a2, LARGE_INTEGER *a3)
{
  void *QuadPart; // rbx
  LONGLONG v5; // r14
  LARGE_INTEGER v6; // rdi
  __int64 v9; // rcx
  unsigned int v10; // esi
  int v11; // eax
  int v12; // eax
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  HANDLE ProcessHeap; // rax
  LONGLONG v18; // [rsp+30h] [rbp-40h] BYREF
  LARGE_INTEGER Frequency; // [rsp+38h] [rbp-38h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp-30h] BYREF
  __int128 v21; // [rsp+48h] [rbp-28h] BYREF
  LPCWCH lpWideCharStr[3]; // [rsp+58h] [rbp-18h]
  unsigned int v23; // [rsp+A0h] [rbp+30h] BYREF
  LARGE_INTEGER v24; // [rsp+B8h] [rbp+48h] BYREF

  QuadPart = 0;
  v5 = 0;
  v24.QuadPart = 0;
  v6.QuadPart = 0;
  v18 = 0;
  Frequency.QuadPart = 0;
  v23 = 0;
  v21 = 0;
  *(_OWORD *)lpWideCharStr = 0;
  QueryPerformanceCounter(&PerformanceCount);
  if ( a1 && (a2 || a3) )
  {
    v11 = ClipCallServer(a1, L"ClipCallServerGatherDiagnostics", 0, (LONGLONG)&v18);
    v5 = v18;
    v10 = v11;
    if ( v11 < 0
      || (v11 = (*(__int64 (__fastcall **)(LONGLONG, const wchar_t *, __int128 *))(*(_QWORD *)v18 + 48LL))(
                  v18,
                  L"DiagXml",
                  &v21),
          v10 = v11,
          v11 < 0)
      || a2
      && ((v11 = sub_180006390(a2), v6 = Frequency, v10 = v11, v11 < 0)
       || (v11 = sub_18001B8C4((LPCWSTR)Frequency.QuadPart, lpWideCharStr[0]), v10 = v11, v11 < 0)) )
    {
      v9 = (unsigned int)v11;
    }
    else
    {
      if ( !a3 )
        goto LABEL_22;
      v12 = sub_18001B434(0xFDE9u, lpWideCharStr[0]);
      v10 = v12;
      if ( v12 >= 0 )
      {
        if ( v23 > 1 )
        {
          *a3 = v24;
          goto LABEL_22;
        }
        v10 = -2147024774;
        v9 = 2147942522LL;
      }
      else
      {
        v9 = (unsigned int)v12;
      }
      QuadPart = (void *)v24.QuadPart;
    }
  }
  else
  {
    v9 = 2147942487LL;
    v10 = -2147024809;
  }
  sub_180002B3C(v9);
  if ( (unsigned int)dword_180030048 > 5
    && (qword_180030058 & 0x400000000000LL) != 0
    && (qword_180030060 & 0x400000000000LL) == qword_180030060 )
  {
    Frequency.QuadPart = 0;
    v24.QuadPart = 0;
    QueryPerformanceCounter(&v24);
    QueryPerformanceFrequency(&Frequency);
    v23 = v10;
    v18 = 1000000 * (v24.QuadPart - PerformanceCount.QuadPart) / Frequency.QuadPart;
    sub_180001140(v13, (unsigned int)byte_18002C5DD, v14, v15, (__int64)&v23, (__int64)&v18);
  }
LABEL_22:
  sub_1800031AC(v10);
  if ( v6.QuadPart )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v6.QuadPart - 4));
    sub_1800031AC(0);
  }
  if ( QuadPart )
    LocalFree(QuadPart);
  if ( v5 )
    (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)v5 + 16LL))(v5);
  return v10;
}

```

## disassembly

```asm
0x18001eb10  mov     [rsp-28h+arg_8], rbx
0x18001eb15  mov     [rsp-28h+arg_10], rsi
0x18001eb1a  push    rbp
0x18001eb1b  push    rdi
0x18001eb1c  push    r12
0x18001eb1e  push    r14
0x18001eb20  push    r15
0x18001eb22  mov     rbp, rsp
0x18001eb25  sub     rsp, 70h
0x18001eb29  xorps   xmm0, xmm0
0x18001eb2c  mov     rsi, rcx
0x18001eb2f  xor     ebx, ebx
0x18001eb31  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18001eb35  xor     r14d, r14d
0x18001eb38  mov     qword ptr [rbp+arg_18], rbx
0x18001eb3c  xor     edi, edi
0x18001eb3e  mov     [rbp+var_40], r14
0x18001eb42  mov     qword ptr [rbp+Frequency], rdi
0x18001eb46  mov     r12, r8
0x18001eb49  mov     [rbp+arg_0], ebx
0x18001eb4c  mov     r15, rdx
0x18001eb4f  movups  [rbp+var_28], xmm0
0x18001eb53  movups  xmmword ptr [rbp+lpWideCharStr], xmm0
0x18001eb57  call    cs:QueryPerformanceCounter
0x18001eb5d  test    rsi, rsi
0x18001eb60  jnz     short loc_18001EB6E
0x18001eb62  mov     ecx, 80070057h
0x18001eb67  mov     esi, ecx
0x18001eb69  jmp     loc_18001EC2A
0x18001eb6e  test    r15, r15
0x18001eb71  jnz     short loc_18001EB78
0x18001eb73  test    r12, r12
0x18001eb76  jz      short loc_18001EB62
0x18001eb78  lea     r9, [rbp+var_40]
0x18001eb7c  xor     r8d, r8d
0x18001eb7f  lea     rdx, aClipcallserver_1; "ClipCallServerGatherDiagnostics"
0x18001eb86  mov     rcx, rsi
0x18001eb89  call    ClipCallServer
0x18001eb8e  mov     r14, [rbp+var_40]
0x18001eb92  mov     esi, eax
0x18001eb94  test    eax, eax
0x18001eb96  jns     short loc_18001EB9F
0x18001eb98  mov     ecx, eax
0x18001eb9a  jmp     loc_18001EC2A
0x18001eb9f  mov     rax, [r14]
0x18001eba2  lea     r8, [rbp+var_28]
0x18001eba6  lea     rdx, aDiagxml; "DiagXml"
0x18001ebad  mov     rcx, r14
0x18001ebb0  mov     rax, [rax+30h]
0x18001ebb4  call    j__guard_dispatch_icall
0x18001ebb9  mov     esi, eax
0x18001ebbb  test    eax, eax
0x18001ebbd  js      short loc_18001EB98
0x18001ebbf  test    r15, r15
0x18001ebc2  jz      short loc_18001EBEC
0x18001ebc4  lea     rdx, [rbp+Frequency]
0x18001ebc8  mov     rcx, r15; lpSrc
0x18001ebcb  call    sub_180006390
0x18001ebd0  mov     rdi, qword ptr [rbp+Frequency]
0x18001ebd4  mov     esi, eax
0x18001ebd6  test    eax, eax
0x18001ebd8  js      short loc_18001EB98
0x18001ebda  mov     rdx, [rbp+lpWideCharStr]; lpWideCharStr
0x18001ebde  mov     rcx, rdi; lpFileName
0x18001ebe1  call    sub_18001B8C4
0x18001ebe6  mov     esi, eax
0x18001ebe8  test    eax, eax
0x18001ebea  js      short loc_18001EB98
0x18001ebec  test    r12, r12
0x18001ebef  jz      loc_18001ECCE
0x18001ebf5  mov     rdx, [rbp+lpWideCharStr]; lpWideCharStr
0x18001ebf9  lea     r9, [rbp+arg_0]
0x18001ebfd  lea     r8, [rbp+arg_18]
0x18001ec01  mov     ecx, 0FDE9h; CodePage
0x18001ec06  call    sub_18001B434
0x18001ec0b  mov     esi, eax
0x18001ec0d  test    eax, eax
0x18001ec0f  jns     short loc_18001EC15
0x18001ec11  mov     ecx, eax
0x18001ec13  jmp     short loc_18001EC26
0x18001ec15  cmp     [rbp+arg_0], 1
0x18001ec19  ja      loc_18001ECC6
0x18001ec1f  mov     esi, 8007007Ah
0x18001ec24  mov     ecx, esi
0x18001ec26  mov     rbx, qword ptr [rbp+arg_18]
0x18001ec2a  call    sub_180002B3C
0x18001ec2f  mov     ecx, cs:dword_180030048
0x18001ec35  cmp     ecx, 5
0x18001ec38  jbe     loc_18001ECCE
0x18001ec3e  mov     rcx, cs:qword_180030060
0x18001ec45  mov     rdx, 400000000000h
0x18001ec4f  mov     rax, cs:qword_180030058
0x18001ec56  test    rdx, rax
0x18001ec59  jz      short loc_18001ECCE
0x18001ec5b  mov     rax, rcx
0x18001ec5e  and     rax, rdx
0x18001ec61  cmp     rax, rcx
0x18001ec64  jnz     short loc_18001ECCE
0x18001ec66  lea     rcx, [rbp+arg_18]; lpPerformanceCount
0x18001ec6a  mov     qword ptr [rbp+Frequency], 0
0x18001ec72  mov     qword ptr [rbp+arg_18], 0
0x18001ec7a  call    cs:QueryPerformanceCounter
0x18001ec80  lea     rcx, [rbp+Frequency]; lpFrequency
0x18001ec84  call    cs:QueryPerformanceFrequency
0x18001ec8a  mov     rax, qword ptr [rbp+arg_18]
0x18001ec8e  sub     rax, qword ptr [rbp+PerformanceCount]
0x18001ec92  imul    rax, 0F4240h
0x18001ec99  mov     [rbp+arg_0], esi
0x18001ec9c  cqo
0x18001ec9e  idiv    qword ptr [rbp+Frequency]
0x18001eca2  lea     rdx, byte_18002C5DD
0x18001eca9  mov     [rbp+var_40], rax
0x18001ecad  lea     rax, [rbp+var_40]
0x18001ecb1  mov     [rsp+70h+var_48], rax
0x18001ecb6  lea     rax, [rbp+arg_0]
0x18001ecba  mov     [rsp+70h+var_50], rax
0x18001ecbf  call    sub_180001140
0x18001ecc4  jmp     short loc_18001ECCE
0x18001ecc6  mov     rax, qword ptr [rbp+arg_18]
0x18001ecca  mov     [r12], rax
0x18001ecce  mov     ecx, esi
0x18001ecd0  call    sub_1800031AC
0x18001ecd5  test    rdi, rdi
0x18001ecd8  jz      short loc_18001ECF6
0x18001ecda  call    cs:GetProcessHeap
0x18001ece0  lea     r8, [rdi-4]; lpMem
0x18001ece4  xor     edx, edx; dwFlags
0x18001ece6  mov     rcx, rax; hHeap
0x18001ece9  call    cs:HeapFree
0x18001ecef  xor     ecx, ecx
0x18001ecf1  call    sub_1800031AC
0x18001ecf6  test    rbx, rbx
0x18001ecf9  jz      short loc_18001ED04
0x18001ecfb  mov     rcx, rbx; hMem
0x18001ecfe  call    cs:__imp_LocalFree
0x18001ed04  test    r14, r14
0x18001ed07  jz      short loc_18001ED18
0x18001ed09  mov     rax, [r14]
0x18001ed0c  mov     rcx, r14
0x18001ed0f  mov     rax, [rax+10h]
0x18001ed13  call    j__guard_dispatch_icall
0x18001ed18  lea     r11, [rsp+70h+var_s0]
0x18001ed1d  mov     eax, esi
0x18001ed1f  mov     rbx, [r11+38h]
0x18001ed23  mov     rsi, [r11+40h]
0x18001ed27  mov     rsp, r11
0x18001ed2a  pop     r15
0x18001ed2c  pop     r14
0x18001ed2e  pop     r12
0x18001ed30  pop     rdi
0x18001ed31  pop     rbp
0x18001ed32  retn
```
