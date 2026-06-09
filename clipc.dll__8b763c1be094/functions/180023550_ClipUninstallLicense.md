# ClipUninstallLicense

- ea: `0x180023550`
- end: `0x1800236d1`
- name: `ClipUninstallLicense`
- size: `385`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x180001140`
- `0x180002b3c`
- `0x1800031ac`
- `0x18001a810`
- `0x180023550`
- `0x1800246b4`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18002364e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18002364e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002357d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180023644`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002357d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180023644`

## pseudocode

```c
__int64 __fastcall ClipUninstallLicense(__int64 a1, __int64 a2)
{
  __int64 v4; // rcx
  unsigned int v5; // ebx
  int v6; // eax
  int v7; // eax
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  LARGE_INTEGER PerformanceCount; // [rsp+30h] [rbp-30h] BYREF
  LONGLONG v13; // [rsp+38h] [rbp-28h] BYREF
  __int64 v14; // [rsp+40h] [rbp-20h]
  __int128 *v15; // [rsp+48h] [rbp-18h]
  __int128 v16; // [rsp+50h] [rbp-10h] BYREF
  unsigned int v17; // [rsp+80h] [rbp+20h] BYREF
  LARGE_INTEGER v18; // [rsp+90h] [rbp+30h] BYREF
  LARGE_INTEGER Frequency; // [rsp+98h] [rbp+38h] BYREF

  v14 = (__int64)&v16 + 8;
  v15 = &v16;
  v16 = 0;
  QueryPerformanceCounter(&PerformanceCount);
  if ( !a1 || !a2 )
  {
    v4 = 2147942487LL;
    v5 = -2147024809;
LABEL_11:
    sub_180002B3C(v4);
    if ( (unsigned int)dword_180030048 > 5
      && (qword_180030058 & 0x400000000000LL) != 0
      && (qword_180030060 & 0x400000000000LL) == qword_180030060 )
    {
      Frequency.QuadPart = 0;
      v18.QuadPart = 0;
      QueryPerformanceCounter(&v18);
      QueryPerformanceFrequency(&Frequency);
      v17 = v5;
      v13 = 1000000 * (v18.QuadPart - PerformanceCount.QuadPart) / Frequency.QuadPart;
      sub_180001140(v8, (unsigned int)&unk_18002C818, v9, v10, (__int64)&v17, (__int64)&v13);
    }
    goto LABEL_15;
  }
  v6 = sub_18001A810(v14, 1, 16, a2);
  v5 = v6;
  if ( v6 < 0 )
    sub_180002B3C((unsigned int)v6);
  sub_1800031AC(v5);
  if ( (v5 & 0x80000000) != 0 )
    goto LABEL_10;
  v7 = sub_1800246B4(a1, 1, v14, 0);
  v5 = v7;
  if ( v7 < 0 )
    sub_180002B3C((unsigned int)v7);
  sub_1800031AC(v5);
  if ( (v5 & 0x80000000) != 0 )
  {
LABEL_10:
    v4 = v5;
    goto LABEL_11;
  }
LABEL_15:
  sub_1800031AC(v5);
  if ( *((_QWORD *)&v16 + 1) )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v16 + 1) + 16LL))(*((_QWORD *)&v16 + 1));
    *((_QWORD *)&v16 + 1) = 0;
  }
  if ( (_QWORD)v16 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v16 + 16LL))(v16);
  return v5;
}

```

## disassembly

```asm
0x180023550  push    rbp
0x180023552  push    rbx
0x180023553  push    rdi
0x180023554  mov     rbp, rsp
0x180023557  sub     rsp, 60h
0x18002355b  lea     rax, [rbp+var_10+8]
0x18002355f  mov     rdi, rcx
0x180023562  mov     [rbp+var_20], rax
0x180023566  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18002356a  lea     rax, [rbp+var_10]
0x18002356e  xorps   xmm0, xmm0
0x180023571  mov     [rbp+var_18], rax
0x180023575  mov     rbx, rdx
0x180023578  movdqu  [rbp+var_10], xmm0
0x18002357d  call    cs:QueryPerformanceCounter
0x180023583  test    rdi, rdi
0x180023586  jnz     short loc_180023591
0x180023588  mov     ecx, 80070057h
0x18002358d  mov     ebx, ecx
0x18002358f  jmp     short loc_1800235F4
0x180023591  test    rbx, rbx
0x180023594  jz      short loc_180023588
0x180023596  mov     rcx, [rbp+var_20]
0x18002359a  mov     edx, 1
0x18002359f  mov     r9, rbx
0x1800235a2  lea     r8d, [rdx+0Fh]
0x1800235a6  call    sub_18001A810
0x1800235ab  mov     ebx, eax
0x1800235ad  test    eax, eax
0x1800235af  jns     short loc_1800235B8
0x1800235b1  mov     ecx, eax
0x1800235b3  call    sub_180002B3C
0x1800235b8  mov     ecx, ebx
0x1800235ba  call    sub_1800031AC
0x1800235bf  test    ebx, ebx
0x1800235c1  js      short loc_1800235F2
0x1800235c3  mov     r8, [rbp+var_20]
0x1800235c7  xor     r9d, r9d
0x1800235ca  mov     rcx, rdi
0x1800235cd  lea     edx, [r9+1]
0x1800235d1  call    sub_1800246B4
0x1800235d6  mov     ebx, eax
0x1800235d8  test    eax, eax
0x1800235da  jns     short loc_1800235E3
0x1800235dc  mov     ecx, eax
0x1800235de  call    sub_180002B3C
0x1800235e3  mov     ecx, ebx
0x1800235e5  call    sub_1800031AC
0x1800235ea  test    ebx, ebx
0x1800235ec  jns     loc_18002368E
0x1800235f2  mov     ecx, ebx
0x1800235f4  call    sub_180002B3C
0x1800235f9  mov     ecx, cs:dword_180030048
0x1800235ff  cmp     ecx, 5
0x180023602  jbe     loc_18002368E
0x180023608  mov     rcx, cs:qword_180030060
0x18002360f  mov     rdx, 400000000000h
0x180023619  mov     rax, cs:qword_180030058
0x180023620  test    rdx, rax
0x180023623  jz      short loc_18002368E
0x180023625  mov     rax, rcx
0x180023628  and     rax, rdx
0x18002362b  cmp     rax, rcx
0x18002362e  jnz     short loc_18002368E
0x180023630  lea     rcx, [rbp+arg_10]; lpPerformanceCount
0x180023634  mov     qword ptr [rbp+Frequency], 0
0x18002363c  mov     qword ptr [rbp+arg_10], 0
0x180023644  call    cs:QueryPerformanceCounter
0x18002364a  lea     rcx, [rbp+Frequency]; lpFrequency
0x18002364e  call    cs:QueryPerformanceFrequency
0x180023654  mov     rax, qword ptr [rbp+arg_10]
0x180023658  sub     rax, qword ptr [rbp+PerformanceCount]
0x18002365c  imul    rax, 0F4240h
0x180023663  mov     [rbp+arg_0], ebx
0x180023666  cqo
0x180023668  idiv    qword ptr [rbp+Frequency]
0x18002366c  lea     rdx, unk_18002C818
0x180023673  mov     [rbp+var_28], rax
0x180023677  lea     rax, [rbp+var_28]
0x18002367b  mov     [rsp+60h+var_38], rax
0x180023680  lea     rax, [rbp+arg_0]
0x180023684  mov     [rsp+60h+var_40], rax
0x180023689  call    sub_180001140
0x18002368e  mov     ecx, ebx
0x180023690  call    sub_1800031AC
0x180023695  mov     rcx, qword ptr [rbp+var_10+8]
0x180023699  test    rcx, rcx
0x18002369c  jz      short loc_1800236B2
0x18002369e  mov     rax, [rcx]
0x1800236a1  mov     rax, [rax+10h]
0x1800236a5  call    j__guard_dispatch_icall
0x1800236aa  mov     qword ptr [rbp+var_10+8], 0
0x1800236b2  mov     rcx, qword ptr [rbp+var_10]
0x1800236b6  test    rcx, rcx
0x1800236b9  jz      short loc_1800236C7
0x1800236bb  mov     rdx, [rcx]
0x1800236be  mov     rax, [rdx+10h]
0x1800236c2  call    j__guard_dispatch_icall
0x1800236c7  mov     eax, ebx
0x1800236c9  add     rsp, 60h
0x1800236cd  pop     rdi
0x1800236ce  pop     rbx
0x1800236cf  pop     rbp
0x1800236d0  retn
```
