# OnQueryResultUpdateStub(_DEV_QUERY_RESULT_ACTION,ushort const *,ulong,_DEVPROPERTY * const,void *)

- ea: `0x140009e3c`
- end: `0x14000a261`
- name: `?OnQueryResultUpdateStub@@YAJW4_DEV_QUERY_RESULT_ACTION@@PEBGKQEAU_DEVPROPERTY@@PEAX@Z`
- size: `1061`
- prototype: `__int64 __fastcall(int, const unsigned __int16 *, unsigned int, char *, struct _PROVIDER_QUERY_ENTRY *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x140017000`

## callees

- `0x140008eec`
- `0x140008f88`
- `0x140009be0`
- `0x140009e3c`
- `0x14000a8ac`
- `0x14000ae30`
- `0x14001a83c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140009ec0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140009efb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140009f8d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140009fdf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000a088`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000a0e6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140009ec0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140009efb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140009f8d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140009fdf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000a088`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000a0e6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a170`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a18c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a1a5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a1d9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a1f7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a212`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a170`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a18c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a1a5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a1d9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a1f7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a212`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009eb1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009eec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009f7e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009fd1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a064`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a0d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a162`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a17e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a197`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a1cb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a1e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a204`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009eb1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009eec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009f7e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009fd1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a064`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a0d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a162`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a17e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a197`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a1cb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a1e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a204`

## pseudocode

```c
__int64 __fastcall OnQueryResultUpdateStub(
        int a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        char *a4,
        struct _PROVIDER_QUERY_ENTRY *a5)
{
  __int64 v6; // r14
  int v9; // edx
  int v10; // r8d
  int v11; // r9d
  HANDLE ProcessHeap; // rax
  int v13; // edx
  int v14; // r8d
  struct _DAS_HOST_QUERY_RESULT *v15; // r13
  signed int v16; // ebx
  unsigned __int16 *v17; // r15
  _QWORD *v18; // rsi
  HANDLE v19; // rax
  _OWORD *v20; // rdi
  const unsigned __int16 *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rbx
  HANDLE v24; // rax
  unsigned __int16 *v25; // rax
  __int64 v26; // r11
  HANDLE v27; // rax
  _QWORD *v28; // rax
  unsigned int v29; // r15d
  __int64 v30; // rcx
  __int64 v31; // rbp
  _WORD *v32; // rax
  __int64 v33; // r15
  HANDLE v34; // rax
  __int64 v35; // rbx
  void *v36; // rax
  unsigned int v37; // ebx
  HANDLE v38; // rax
  void *v39; // rax
  HANDLE v40; // rax
  HANDLE v41; // rax
  HANDLE v42; // rax
  unsigned int i; // ebp
  void *v44; // r15
  HANDLE v45; // rax
  void *v46; // rdi
  HANDLE v47; // rax
  HANDLE v48; // rax
  int MessageGuid; // [rsp+20h] [rbp-88h]
  int v51; // [rsp+28h] [rbp-80h]
  unsigned int v52; // [rsp+40h] [rbp-68h]
  unsigned __int16 *v53; // [rsp+48h] [rbp-60h]
  __int64 v54; // [rsp+50h] [rbp-58h]
  __int64 v55; // [rsp+50h] [rbp-58h]

  v6 = a3;
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      (int)a2,
      a3,
      32,
      &WPP_92038ab37ee4317b05ca4ff2fd992641_Traceguids);
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_Sdd(*((_QWORD *)WPP_GLOBAL_Control + 5), v9, v10, v11, MessageGuid, (__int64)a2, a1, v6);
  }
  ProcessHeap = GetProcessHeap();
  v15 = (struct _DAS_HOST_QUERY_RESULT *)HeapAlloc(ProcessHeap, 0, 0x18u);
  if ( !v15 )
  {
    v16 = -2147024882;
    goto LABEL_47;
  }
  v17 = 0;
  *(_OWORD *)v15 = 0;
  *((_QWORD *)v15 + 2) = 0;
  v18 = 0;
  v19 = GetProcessHeap();
  v20 = HeapAlloc(v19, 0, 0x28u);
  if ( !v20 )
  {
LABEL_7:
    v16 = -2147024882;
    goto LABEL_37;
  }
  *v20 = 0;
  v20[1] = 0;
  *((_QWORD *)v20 + 4) = 0;
  *(_DWORD *)v20 = a1;
  *((_DWORD *)v20 + 2) = 5;
  if ( !a2 )
  {
    v16 = -2147024809;
    goto LABEL_37;
  }
  v21 = a2;
  v22 = 0x7FFFFFFF;
  do
  {
    if ( !*v21 )
      break;
    ++v21;
    --v22;
  }
  while ( v22 );
  v16 = v22 == 0 ? 0x80070057 : 0;
  if ( v22 )
  {
    v23 = -(__int64)(v22 != 0) & (2 * (0x7FFFFFFF - v22));
    v24 = GetProcessHeap();
    v25 = (unsigned __int16 *)HeapAlloc(v24, 0, v23 + 2);
    v53 = v25;
    v17 = v25;
    if ( !v25 )
      goto LABEL_7;
    v16 = StringCbCopyW(v25, v23 + 2, a2);
    if ( v16 < 0 )
      goto LABEL_37;
    *((_QWORD *)v20 + 2) = v17;
    if ( (_DWORD)v6 )
    {
      v27 = GetProcessHeap();
      v28 = HeapAlloc(v27, 0, 48 * v6);
      v18 = v28;
      if ( !v28 )
        goto LABEL_7;
      memcpy_0(v28, a4, 48 * v6);
      v26 = 0;
    }
    v52 = v26;
    v29 = v26;
    if ( (_DWORD)v6 )
    {
      do
      {
        v30 = v29;
        v54 = v29;
        v31 = 6LL * v29;
        v32 = *(_WORD **)&a4[48 * v29 + 24];
        if ( v32 )
        {
          v33 = 0x7FFFFFFF;
          do
          {
            if ( *v32 == (_WORD)v26 )
              break;
            ++v32;
            --v33;
          }
          while ( v33 );
          v16 = v33 == 0 ? 0x80070057 : 0;
          if ( !v33 )
            goto LABEL_31;
          v18[v31 + 3] = v26;
          v34 = GetProcessHeap();
          v35 = -(__int64)(v33 != 0) & (2 * (0x7FFFFFFF - v33));
          v36 = HeapAlloc(v34, 0, v35 + 2);
          v18[v31 + 3] = v36;
          if ( !v36 )
            goto LABEL_33;
          memcpy_0(v36, *(const void **)&a4[8 * v31 + 24], v35 + 2);
          v30 = v54;
          v26 = 0;
          v29 = v52;
        }
        if ( *(_QWORD *)&a4[8 * v31 + 40] != v26 )
        {
          v18[v31 + 5] = v26;
          v55 = 48 * v30;
          v37 = *(_DWORD *)&a4[48 * v30 + 36];
          v38 = GetProcessHeap();
          v39 = HeapAlloc(v38, 0, v37);
          v18[v31 + 5] = v39;
          if ( !v39 )
          {
            HIDWORD(v18[v31 + 4]) = 0;
LABEL_33:
            v16 = -2147024882;
LABEL_34:
            v17 = v53;
            goto LABEL_37;
          }
          memcpy_0(v39, *(const void **)&a4[8 * v31 + 40], *(unsigned int *)&a4[v55 + 36]);
          v26 = 0;
        }
        v52 = ++v29;
      }
      while ( v29 < (unsigned int)v6 );
    }
    *((_DWORD *)v20 + 6) = v6;
    *((_QWORD *)v20 + 4) = v18;
    *((_QWORD *)v15 + 2) = v20;
    v16 = AddToResultList(v15, a5);
LABEL_31:
    if ( v16 < 0 )
      goto LABEL_34;
  }
  else
  {
LABEL_37:
    v40 = GetProcessHeap();
    HeapFree(v40, 0, v15);
    if ( v20 )
    {
      v41 = GetProcessHeap();
      HeapFree(v41, 0, v20);
    }
    if ( v17 )
    {
      v42 = GetProcessHeap();
      HeapFree(v42, 0, v17);
    }
    if ( v18 )
    {
      for ( i = 0; i < (unsigned int)v6; ++i )
      {
        v44 = (void *)v18[6 * i + 3];
        if ( !v44 )
          break;
        v45 = GetProcessHeap();
        HeapFree(v45, 0, v44);
        v46 = (void *)v18[6 * i + 5];
        if ( !v46 )
          break;
        v47 = GetProcessHeap();
        HeapFree(v47, 0, v46);
      }
      v48 = GetProcessHeap();
      HeapFree(v48, 0, v18);
    }
  }
LABEL_47:
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v13,
      v14,
      34,
      &WPP_92038ab37ee4317b05ca4ff2fd992641_Traceguids,
      v51,
      v16);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x140009e3c  push    rbx
0x140009e3e  push    rbp
0x140009e3f  push    rsi
0x140009e40  push    rdi
0x140009e41  push    r12
0x140009e43  push    r13
0x140009e45  push    r14
0x140009e47  push    r15
0x140009e49  sub     rsp, 68h
0x140009e4d  mov     r12, r9
0x140009e50  mov     r14d, r8d
0x140009e53  mov     rbp, rdx
0x140009e56  mov     ebx, ecx
0x140009e58  lea     r13, WPP_RECORDER_INITIALIZED
0x140009e5f  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140009e66  lea     rdi, WPP_92038ab37ee4317b05ca4ff2fd992641_Traceguids
0x140009e6d  jz      short loc_140009EB1
0x140009e6f  mov     rcx, cs:WPP_GLOBAL_Control
0x140009e76  mov     r9d, 20h ; ' '; int
0x140009e7c  mov     [rsp+0A8h+MessageGuid], rdi; MessageGuid
0x140009e81  mov     rcx, [rcx+28h]; int
0x140009e85  call    WPP_RECORDER_SF_s
0x140009e8a  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140009e91  jz      short loc_140009EB1
0x140009e93  mov     rcx, cs:WPP_GLOBAL_Control
0x140009e9a  mov     [rsp+0A8h+var_70], r14d
0x140009e9f  mov     dword ptr [rsp+0A8h+var_78], ebx
0x140009ea3  mov     qword ptr [rsp+0A8h+var_80], rbp; int
0x140009ea8  mov     rcx, [rcx+28h]
0x140009eac  call    WPP_RECORDER_SF_Sdd
0x140009eb1  call    cs:__imp_GetProcessHeap
0x140009eb7  xor     edx, edx; dwFlags
0x140009eb9  mov     rcx, rax; hHeap
0x140009ebc  lea     r8d, [rdx+18h]; dwBytes
0x140009ec0  call    cs:__imp_HeapAlloc
0x140009ec6  mov     r13, rax
0x140009ec9  xor     eax, eax
0x140009ecb  test    r13, r13
0x140009ece  jnz     short loc_140009EDA
0x140009ed0  mov     ebx, 8007000Eh
0x140009ed5  jmp     loc_14000A21F
0x140009eda  xorps   xmm0, xmm0
0x140009edd  mov     r15, rax
0x140009ee0  movups  xmmword ptr [r13+0], xmm0
0x140009ee5  mov     [r13+10h], rax
0x140009ee9  mov     rsi, rax
0x140009eec  call    cs:__imp_GetProcessHeap
0x140009ef2  xor     edx, edx; dwFlags
0x140009ef4  mov     rcx, rax; hHeap
0x140009ef7  lea     r8d, [rdx+28h]; dwBytes
0x140009efb  call    cs:__imp_HeapAlloc
0x140009f01  xor     ecx, ecx
0x140009f03  mov     rdi, rax
0x140009f06  test    rax, rax
0x140009f09  jnz     short loc_140009F15
0x140009f0b  mov     ebx, 8007000Eh
0x140009f10  jmp     loc_14000A162
0x140009f15  xorps   xmm0, xmm0
0x140009f18  xor     eax, eax
0x140009f1a  movups  xmmword ptr [rdi], xmm0
0x140009f1d  movups  xmmword ptr [rdi+10h], xmm0
0x140009f21  mov     [rdi+20h], rax
0x140009f25  mov     [rdi], ebx
0x140009f27  mov     dword ptr [rdi+8], 5
0x140009f2e  test    rbp, rbp
0x140009f31  jz      loc_14000A15D
0x140009f37  mov     r8d, 7FFFFFFFh
0x140009f3d  mov     rax, rbp
0x140009f40  mov     edx, r8d
0x140009f43  cmp     [rax], cx
0x140009f46  jz      short loc_140009F52
0x140009f48  add     rax, 2
0x140009f4c  sub     rdx, 1
0x140009f50  jnz     short loc_140009F43
0x140009f52  mov     rax, rdx
0x140009f55  neg     rax
0x140009f58  sbb     ebx, ebx
0x140009f5a  not     ebx
0x140009f5c  and     ebx, 80070057h
0x140009f62  test    rdx, rdx
0x140009f65  jz      loc_14000A162
0x140009f6b  mov     rcx, r8
0x140009f6e  sub     rcx, rdx
0x140009f71  neg     rdx
0x140009f74  sbb     rax, rax
0x140009f77  lea     rbx, [rcx+rcx]
0x140009f7b  and     rbx, rax
0x140009f7e  call    cs:__imp_GetProcessHeap
0x140009f84  lea     r8, [rbx+2]; dwBytes
0x140009f88  xor     edx, edx; dwFlags
0x140009f8a  mov     rcx, rax; hHeap
0x140009f8d  call    cs:__imp_HeapAlloc
0x140009f93  xor     r11d, r11d
0x140009f96  mov     [rsp+0A8h+var_60], rax
0x140009f9b  mov     r15, rax
0x140009f9e  test    rax, rax
0x140009fa1  jz      loc_140009F0B
0x140009fa7  mov     r8, rbp; unsigned __int16 *
0x140009faa  lea     rdx, [rbx+2]; unsigned __int64
0x140009fae  mov     rcx, rax; unsigned __int16 *
0x140009fb1  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x140009fb6  mov     ebx, eax
0x140009fb8  test    eax, eax
0x140009fba  js      loc_14000A162
0x140009fc0  mov     [rdi+10h], r15
0x140009fc4  test    r14d, r14d
0x140009fc7  jz      short loc_14000A002
0x140009fc9  lea     rbx, [r14+r14*2]
0x140009fcd  shl     rbx, 4
0x140009fd1  call    cs:__imp_GetProcessHeap
0x140009fd7  mov     r8, rbx; dwBytes
0x140009fda  xor     edx, edx; dwFlags
0x140009fdc  mov     rcx, rax; hHeap
0x140009fdf  call    cs:__imp_HeapAlloc
0x140009fe5  mov     rsi, rax
0x140009fe8  test    rax, rax
0x140009feb  jz      loc_140009F0B
0x140009ff1  mov     r8, rbx; Size
0x140009ff4  mov     rdx, r12; Src
0x140009ff7  mov     rcx, rax; void *
0x140009ffa  call    memcpy_0
0x140009fff  xor     r11d, r11d
0x14000a002  mov     [rsp+0A8h+var_68], r11d
0x14000a007  mov     r15d, r11d
0x14000a00a  test    r14d, r14d
0x14000a00d  jz      loc_14000A123
0x14000a013  mov     ecx, r15d
0x14000a016  mov     [rsp+0A8h+var_58], rcx
0x14000a01b  lea     rbp, [rcx+rcx*2]
0x14000a01f  add     rbp, rbp
0x14000a022  mov     rax, [r12+rbp*8+18h]
0x14000a027  test    rax, rax
0x14000a02a  jz      loc_14000A0BA
0x14000a030  mov     r15d, 7FFFFFFFh
0x14000a036  cmp     [rax], r11w
0x14000a03a  jz      short loc_14000A046
0x14000a03c  add     rax, 2
0x14000a040  sub     r15, 1
0x14000a044  jnz     short loc_14000A036
0x14000a046  mov     rax, r15
0x14000a049  neg     rax
0x14000a04c  sbb     ebx, ebx
0x14000a04e  not     ebx
0x14000a050  and     ebx, 80070057h
0x14000a056  test    r15, r15
0x14000a059  jz      loc_14000A141
0x14000a05f  mov     [rsi+rbp*8+18h], r11
0x14000a064  call    cs:__imp_GetProcessHeap
0x14000a06a  mov     edx, 7FFFFFFFh
0x14000a06f  sub     rdx, r15
0x14000a072  neg     r15
0x14000a075  sbb     rcx, rcx
0x14000a078  lea     rbx, [rdx+rdx]
0x14000a07c  xor     edx, edx; dwFlags
0x14000a07e  and     rbx, rcx
0x14000a081  mov     rcx, rax; hHeap
0x14000a084  lea     r8, [rbx+2]; dwBytes
0x14000a088  call    cs:__imp_HeapAlloc
0x14000a08e  mov     [rsi+rbp*8+18h], rax
0x14000a093  test    rax, rax
0x14000a096  jz      loc_14000A14B
0x14000a09c  mov     rdx, [r12+rbp*8+18h]; Src
0x14000a0a1  lea     r8, [rbx+2]; Size
0x14000a0a5  mov     rcx, rax; void *
0x14000a0a8  call    memcpy_0
0x14000a0ad  mov     rcx, [rsp+0A8h+var_58]
0x14000a0b2  xor     r11d, r11d
0x14000a0b5  mov     r15d, [rsp+0A8h+var_68]
0x14000a0ba  cmp     [r12+rbp*8+28h], r11
0x14000a0bf  jz      short loc_14000A112
0x14000a0c1  lea     rax, [rcx+rcx*2]
0x14000a0c5  mov     [rsi+rbp*8+28h], r11
0x14000a0ca  shl     rax, 4
0x14000a0ce  mov     [rsp+0A8h+var_58], rax
0x14000a0d3  mov     ebx, [rax+r12+24h]
0x14000a0d8  call    cs:__imp_GetProcessHeap
0x14000a0de  mov     r8d, ebx; dwBytes
0x14000a0e1  xor     edx, edx; dwFlags
0x14000a0e3  mov     rcx, rax; hHeap
0x14000a0e6  call    cs:__imp_HeapAlloc
0x14000a0ec  xor     ecx, ecx
0x14000a0ee  mov     [rsi+rbp*8+28h], rax
0x14000a0f3  test    rax, rax
0x14000a0f6  jz      short loc_14000A157
0x14000a0f8  mov     rcx, [rsp+0A8h+var_58]
0x14000a0fd  mov     rdx, [r12+rbp*8+28h]; Src
0x14000a102  mov     r8d, [rcx+r12+24h]; Size
0x14000a107  mov     rcx, rax; void *
0x14000a10a  call    memcpy_0
0x14000a10f  xor     r11d, r11d
0x14000a112  inc     r15d
0x14000a115  mov     [rsp+0A8h+var_68], r15d
0x14000a11a  cmp     r15d, r14d
0x14000a11d  jb      loc_14000A013
0x14000a123  mov     rdx, [rsp+0A8h+arg_20]; struct _PROVIDER_QUERY_ENTRY *
0x14000a12b  mov     rcx, r13; struct _DAS_HOST_QUERY_RESULT *
0x14000a12e  mov     [rdi+18h], r14d
0x14000a132  mov     [rdi+20h], rsi
0x14000a136  mov     [r13+10h], rdi
0x14000a13a  call    ?AddToResultList@@YAJPEAU_DAS_HOST_QUERY_RESULT@@PEAU_PROVIDER_QUERY_ENTRY@@@Z; AddToResultList(_DAS_HOST_QUERY_RESULT *,_PROVIDER_QUERY_ENTRY *)
0x14000a13f  mov     ebx, eax
0x14000a141  test    ebx, ebx
0x14000a143  jns     loc_14000A218
0x14000a149  jmp     short loc_14000A150
0x14000a14b  mov     ebx, 8007000Eh
0x14000a150  mov     r15, [rsp+0A8h+var_60]
0x14000a155  jmp     short loc_14000A162
0x14000a157  mov     [rsi+rbp*8+24h], ecx
0x14000a15b  jmp     short loc_14000A14B
0x14000a15d  mov     ebx, 80070057h
0x14000a162  call    cs:__imp_GetProcessHeap
0x14000a168  mov     r8, r13; lpMem
0x14000a16b  xor     edx, edx; dwFlags
0x14000a16d  mov     rcx, rax; hHeap
0x14000a170  call    cs:__imp_HeapFree
0x14000a176  xor     r13d, r13d
0x14000a179  test    rdi, rdi
0x14000a17c  jz      short loc_14000A192
0x14000a17e  call    cs:__imp_GetProcessHeap
0x14000a184  mov     r8, rdi; lpMem
0x14000a187  xor     edx, edx; dwFlags
0x14000a189  mov     rcx, rax; hHeap
0x14000a18c  call    cs:__imp_HeapFree
0x14000a192  test    r15, r15
0x14000a195  jz      short loc_14000A1AB
0x14000a197  call    cs:__imp_GetProcessHeap
0x14000a19d  mov     r8, r15; lpMem
0x14000a1a0  xor     edx, edx; dwFlags
0x14000a1a2  mov     rcx, rax; hHeap
0x14000a1a5  call    cs:__imp_HeapFree
0x14000a1ab  test    rsi, rsi
0x14000a1ae  jz      short loc_14000A218
0x14000a1b0  mov     ebp, r13d
0x14000a1b3  test    r14d, r14d
0x14000a1b6  jz      short loc_14000A204
0x14000a1b8  mov     eax, ebp
0x14000a1ba  lea     rdi, [rax+rax*2]
0x14000a1be  add     rdi, rdi
0x14000a1c1  mov     r15, [rsi+rdi*8+18h]
0x14000a1c6  test    r15, r15
0x14000a1c9  jz      short loc_14000A204
0x14000a1cb  call    cs:__imp_GetProcessHeap
0x14000a1d1  mov     r8, r15; lpMem
0x14000a1d4  xor     edx, edx; dwFlags
0x14000a1d6  mov     rcx, rax; hHeap
0x14000a1d9  call    cs:__imp_HeapFree
0x14000a1df  mov     rdi, [rsi+rdi*8+28h]
0x14000a1e4  test    rdi, rdi
0x14000a1e7  jz      short loc_14000A204
0x14000a1e9  call    cs:__imp_GetProcessHeap
0x14000a1ef  mov     r8, rdi; lpMem
0x14000a1f2  xor     edx, edx; dwFlags
0x14000a1f4  mov     rcx, rax; hHeap
0x14000a1f7  call    cs:__imp_HeapFree
0x14000a1fd  inc     ebp
0x14000a1ff  cmp     ebp, r14d
0x14000a202  jb      short loc_14000A1B8
0x14000a204  call    cs:__imp_GetProcessHeap
0x14000a20a  mov     r8, rsi; lpMem
0x14000a20d  xor     edx, edx; dwFlags
0x14000a20f  mov     rcx, rax; hHeap
0x14000a212  call    cs:__imp_HeapFree
0x14000a218  lea     rdi, WPP_92038ab37ee4317b05ca4ff2fd992641_Traceguids
0x14000a21f  lea     rax, WPP_RECORDER_INITIALIZED
0x14000a226  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000a22d  jz      short loc_14000A24E
0x14000a22f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a236  mov     r9d, 22h ; '"'; int
0x14000a23c  mov     dword ptr [rsp+0A8h+var_78], ebx; char
0x14000a240  mov     [rsp+0A8h+MessageGuid], rdi; MessageGuid
0x14000a245  mov     rcx, [rcx+28h]; int
0x14000a249  call    WPP_RECORDER_SF_sd
0x14000a24e  mov     eax, ebx
0x14000a250  add     rsp, 68h
0x14000a254  pop     r15
0x14000a256  pop     r14
0x14000a258  pop     r13
0x14000a25a  pop     r12
0x14000a25c  pop     rdi
0x14000a25d  pop     rsi
0x14000a25e  pop     rbp
0x14000a25f  pop     rbx
0x14000a260  retn
```
