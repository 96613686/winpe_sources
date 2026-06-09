# WriteMemoryCompressed(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *,_INTERNAL_PROCESS *)

- ea: `0x18000d6f4`
- end: `0x18000dc71`
- name: `?WriteMemoryCompressed@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@PEAU_INTERNAL_PROCESS@@@Z`
- size: `1405`
- prototype: `__int64 __fastcall(struct _MINIDUMP_STATE *, struct _MINIDUMP_STREAM_INFO *, struct _INTERNAL_PROCESS *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000c19c`

## callees

- `0x180001710`
- `0x180001ae0`
- `0x1800021f4`
- `0x180004414`
- `0x18000449c`
- `0x180004560`
- `0x180006b0c`
- `0x18000d6f4`
- `0x18001951c`
- `0x18001db40`
- `0x18001ddd8`
- `0x18001e8f0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000d918`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000d918`

## string_xrefs

- `0x18000d736`: `WriteMemoryCompressed`
- `0x18000dbe7`: `WriteMemoryCompressed`
- `0x18000daf8`: `WriteFullMemoryCompressed.QueryVirtual(0x%I64x) for info failed, 0x%08x`
- `0x18000db29`: `AppendCompressedMemoryStream failed.`
- `0x18000dbc2`: `AppendCompressedMemoryStream completed successfully.`

## pseudocode

```c
__int64 __fastcall WriteMemoryCompressed(
        struct _MINIDUMP_STATE *a1,
        struct _MINIDUMP_STREAM_INFO *a2,
        struct _INTERNAL_PROCESS *a3)
{
  int v5; // ebx
  int v6; // ecx
  unsigned __int64 v7; // rbx
  unsigned int v8; // ebx
  ULONG64 BaseAddress; // rsi
  ULONG64 v10; // rbx
  int v11; // r15d
  __int64 RegionSize; // rbx
  __int64 v13; // rax
  __int64 v14; // rbx
  CompressedStreamDump::DumpWriter *v15; // rdi
  __int128 v17; // [rsp+38h] [rbp-D0h]
  __int128 v18; // [rsp+48h] [rbp-C0h]
  __int128 v19; // [rsp+68h] [rbp-A0h]
  __int64 v20; // [rsp+78h] [rbp-90h]
  __int128 v21; // [rsp+88h] [rbp-80h] BYREF
  __int128 v22; // [rsp+98h] [rbp-70h]
  __int128 v23; // [rsp+A8h] [rbp-60h]
  int v24; // [rsp+B8h] [rbp-50h]
  __int64 v25; // [rsp+C0h] [rbp-48h]
  _BYTE v26[12]; // [rsp+C8h] [rbp-40h] BYREF
  int v27; // [rsp+D4h] [rbp-34h]
  __int64 v28; // [rsp+D8h] [rbp-30h]
  int v29; // [rsp+E0h] [rbp-28h]
  struct _MINIDUMP_MEMORY_INFO v30; // [rsp+5E8h] [rbp+4E0h] BYREF
  _OWORD v31[4]; // [rsp+618h] [rbp+510h] BYREF
  __int64 v32; // [rsp+658h] [rbp+550h]
  CompressedStreamDump::DumpWriter *v33; // [rsp+660h] [rbp+558h]
  __int128 v34; // [rsp+668h] [rbp+560h] BYREF
  __int64 v35; // [rsp+678h] [rbp+570h]
  int v36; // [rsp+680h] [rbp+578h]
  _DWORD v37[2]; // [rsp+690h] [rbp+588h] BYREF
  __int64 v38; // [rsp+698h] [rbp+590h]
  ULONGLONG TickCount64; // [rsp+6A0h] [rbp+598h]
  __int64 v40; // [rsp+6A8h] [rbp+5A0h]
  unsigned int v41; // [rsp+6B8h] [rbp+5B0h]
  __int64 v42; // [rsp+6C0h] [rbp+5B8h]
  int v43; // [rsp+6D8h] [rbp+5D0h]
  int v44; // [rsp+720h] [rbp+618h]
  __int64 v45; // [rsp+750h] [rbp+648h] BYREF
  __int128 v46; // [rsp+758h] [rbp+650h]
  __int64 v47; // [rsp+768h] [rbp+660h]
  __int64 v48; // [rsp+770h] [rbp+668h]
  __int64 v49; // [rsp+778h] [rbp+670h]
  __int64 v50; // [rsp+780h] [rbp+678h] BYREF
  __int128 v51; // [rsp+788h] [rbp+680h]

  v25 = -2;
  (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
    *((_QWORD *)a1 + 5),
    1,
    "%ls entered.",
    L"WriteMemoryCompressed");
  HIDWORD(v17) = 4;
  v5 = 0x400000;
  *(_QWORD *)&v18 = 0x400000;
  *((_QWORD *)&v19 + 1) = 0;
  v20 = 0;
  if ( *((_QWORD *)a1 + 8) )
  {
    memset_0(v26, 0, 0x520u);
    v21 = 0;
    v22 = 0;
    v23 = 0;
    v24 = 0;
    v27 = 21;
    if ( (*((unsigned int (__fastcall **)(_QWORD, _BYTE *, __int128 *))a1 + 8))(*((_QWORD *)a1 + 10), v26, &v21) )
    {
      v6 = 4;
      if ( (unsigned int)(v21 - 1) <= 0x7F )
        v6 = v21;
      HIDWORD(v17) = v6;
      if ( (unsigned int)(DWORD1(v21) - 0x100000) <= 0x3F00000 )
        v5 = DWORD1(v21);
      LODWORD(v18) = v5;
      if ( *((_QWORD *)&v21 + 1) && (unsigned int)(v22 - 1) <= 0x7F )
      {
        *((_QWORD *)&v19 + 1) = *((_QWORD *)&v21 + 1);
        LODWORD(v20) = v22;
      }
    }
  }
  *((_QWORD *)&v18 + 1) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)a1 + 3) + 48LL))(*((_QWORD *)a1 + 3));
  *(_QWORD *)&v17 = *(_QWORD *)a1;
  DWORD2(v17) = *((_DWORD *)a1 + 2);
  v7 = *((_QWORD *)a2 + 20);
  *(_QWORD *)&v19 = *((_QWORD *)a1 + 2);
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 64000;
  memset_0(v37, 0, 0xC0u);
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  v31[0] = v17;
  v31[1] = v18;
  v31[3] = v19;
  v32 = v20;
  v31[2] = __PAIR128__(0x10000, v7);
  TickCount64 = GetTickCount64();
  v40 = DWORD2(v31[0]);
  v37[0] = 192;
  v38 = 0x21217A646D702121LL;
  v37[1] = 2;
  v44 = 1;
  memset(&v30, 0, sizeof(v30));
  if ( !CompressedStreamDump::CompressedMemStream::Init((CompressedStreamDump::CompressedMemStream *)v31) )
  {
LABEL_11:
    v8 = -2147467259;
    goto LABEL_42;
  }
  if ( *((_QWORD *)a2 + 20) > 0xFFFFFFFF )
  {
    (*(void (__fastcall **)(_QWORD, __int64, const char *))(**((_QWORD **)a1 + 5) + 8LL))(
      *((_QWORD *)a1 + 5),
      4,
      "Full memory stream RVA overflowed");
    v8 = -2147024809;
    goto LABEL_42;
  }
  BaseAddress = 0;
  v10 = 0;
  v11 = 1;
  while ( BaseAddress || !v10 )
  {
    if ( (unsigned int)GenCheckCancel(a1) )
    {
      v8 = -2147023673;
      goto LABEL_42;
    }
    if ( v10 && BaseAddress <= v10 )
    {
      v30.BaseAddress = BaseAddress;
      RegionSize = v10 - BaseAddress + 1;
      v30.RegionSize = RegionSize;
    }
    else
    {
      v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, ULONG64, struct _MINIDUMP_MEMORY_INFO *))(**((_QWORD **)a1 + 2)
                                                                                              + 248LL))(
             *((_QWORD *)a1 + 2),
             *(_QWORD *)a1,
             BaseAddress,
             &v30);
      if ( v8 )
      {
        if ( v8 != -2147467262 )
        {
          (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
            *((_QWORD *)a1 + 5),
            4,
            "WriteFullMemoryCompressed.QueryVirtual(0x%I64x) for info failed, 0x%08x",
            BaseAddress,
            v8);
          goto LABEL_42;
        }
        break;
      }
      RegionSize = v30.RegionSize;
      BaseAddress = v30.BaseAddress;
    }
    BaseAddress += RegionSize;
    v10 = BaseAddress - 1;
    if ( (v30.Protect & 0x100) == 0
      && (v30.Protect & 1) == 0
      && (v30.State & 0x10000) == 0
      && (v30.State & 0x2000) == 0
      && ((*((_DWORD *)a1 + 14) & 0x1000000) == 0 || (v30.Protect & 0x400) == 0) )
    {
      if ( v11 )
      {
        v11 = FilterVmRegion(a1, &v30);
        if ( v30.RegionSize )
        {
          BaseAddress = v30.RegionSize + v30.BaseAddress;
          goto LABEL_32;
        }
      }
      else
      {
LABEL_32:
        if ( !CompressedStreamDump::CompressedMemStream::AddMemoryRegion(
                (CompressedStreamDump::CompressedMemStream *)v31,
                &v30) )
          goto LABEL_11;
      }
    }
  }
  if ( !CompressedStreamDump::CompressedMemStream::AppendCompressedMemoryStream((CompressedStreamDump::CompressedMemStream *)v31) )
  {
    (*(void (__fastcall **)(_QWORD, __int64, const char *))(**((_QWORD **)a1 + 5) + 8LL))(
      *((_QWORD *)a1 + 5),
      4,
      "AppendCompressedMemoryStream failed.");
    goto LABEL_11;
  }
  v13 = v41;
  *((_DWORD *)a2 + 26) = v41;
  *((_DWORD *)a2 + 27) = 192;
  v14 = v42;
  *((_QWORD *)a2 + 20) = v42 + v13;
  if ( *((_QWORD *)a1 + 8) )
  {
    memset_0(v26, 0, 0x520u);
    v21 = 0;
    v22 = 0;
    v23 = 0;
    v24 = 0;
    v27 = 22;
    v28 = v14;
    v29 = v43;
    (*((void (__fastcall **)(_QWORD, _BYTE *, __int128 *))a1 + 8))(*((_QWORD *)a1 + 10), v26, &v21);
  }
  (*(void (__fastcall **)(_QWORD, __int64, const char *))(**((_QWORD **)a1 + 5) + 8LL))(
    *((_QWORD *)a1 + 5),
    1,
    "AppendCompressedMemoryStream completed successfully.");
  v8 = 0;
LABEL_42:
  (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
    *((_QWORD *)a1 + 5),
    1,
    "%ls exit.",
    L"WriteMemoryCompressed");
  std::vector<MemoryBucket>::~vector<MemoryBucket>(&v50);
  std::vector<MemoryBucket>::~vector<MemoryBucket>(&v45);
  std::vector<MemoryRegion>::~vector<MemoryRegion>(&v34);
  v15 = v33;
  if ( v33 )
  {
    CompressedStreamDump::DumpWriter::~DumpWriter(v33);
    operator delete(v15, 0x38u);
  }
  return v8;
}

```

## disassembly

```asm
0x18000d6f4  mov     rax, rsp
0x18000d6f7  push    rbp
0x18000d6f8  push    rsi
0x18000d6f9  push    rdi
0x18000d6fa  push    r14
0x18000d6fc  push    r15
0x18000d6fe  lea     rbp, [rax-6C8h]
0x18000d705  sub     rsp, 7A0h
0x18000d70c  mov     [rbp+6C0h+var_708], 0FFFFFFFFFFFFFFFEh
0x18000d714  mov     [rax+18h], rbx
0x18000d718  mov     rax, cs:__security_cookie
0x18000d71f  xor     rax, rsp
0x18000d722  mov     [rbp+6C0h+var_30], rax
0x18000d729  mov     r14, rdx
0x18000d72c  mov     rdi, rcx
0x18000d72f  mov     rcx, [rcx+28h]
0x18000d733  mov     rax, [rcx]
0x18000d736  lea     r9, aWritememorycom; "WriteMemoryCompressed"
0x18000d73d  lea     r8, aLsEntered; "%ls entered."
0x18000d744  mov     edx, 1
0x18000d749  mov     rax, [rax+8]
0x18000d74d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d752  mov     esi, 4
0x18000d757  mov     dword ptr [rsp+7C0h+var_788+4], esi
0x18000d75b  mov     ebx, 400000h
0x18000d760  mov     qword ptr [rsp+7C0h+var_788+8], rbx
0x18000d765  mov     qword ptr [rsp+7C0h+var_768], 10000h
0x18000d76e  mov     [rsp+7C0h+var_758], 0
0x18000d777  mov     qword ptr [rsp+70h], 0
0x18000d780  cmp     qword ptr [rdi+40h], 0
0x18000d785  jz      loc_18000D814
0x18000d78b  xor     edx, edx; Val
0x18000d78d  mov     r8d, 520h; Size
0x18000d793  lea     rcx, [rbp+6C0h+var_700]; void *
0x18000d797  call    memset_0
0x18000d79c  xorps   xmm0, xmm0
0x18000d79f  xor     eax, eax
0x18000d7a1  movups  [rbp+6C0h+var_740], xmm0
0x18000d7a5  movups  [rbp+6C0h+var_730], xmm0
0x18000d7a9  movups  [rbp+6C0h+var_720], xmm0
0x18000d7ad  mov     [rbp+6C0h+var_710], eax
0x18000d7b0  mov     [rbp+6C0h+var_6F4], 15h
0x18000d7b7  lea     r8, [rbp+6C0h+var_740]
0x18000d7bb  lea     rdx, [rbp+6C0h+var_700]
0x18000d7bf  mov     rcx, [rdi+50h]
0x18000d7c3  mov     rax, [rdi+40h]
0x18000d7c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7cc  test    eax, eax
0x18000d7ce  jz      short loc_18000D814
0x18000d7d0  mov     edx, dword ptr [rbp+6C0h+var_740]
0x18000d7d3  lea     eax, [rdx-1]
0x18000d7d6  mov     ecx, esi
0x18000d7d8  cmp     eax, 7Fh
0x18000d7db  cmovbe  ecx, edx
0x18000d7de  mov     dword ptr [rsp+7C0h+var_788+4], ecx
0x18000d7e2  mov     ecx, dword ptr [rbp+6C0h+var_740+4]
0x18000d7e5  lea     eax, [rcx-100000h]
0x18000d7eb  cmp     eax, 3F00000h
0x18000d7f0  cmovbe  ebx, ecx
0x18000d7f3  mov     dword ptr [rsp+7C0h+var_788+8], ebx
0x18000d7f7  mov     rdx, qword ptr [rbp+6C0h+var_740+8]
0x18000d7fb  test    rdx, rdx
0x18000d7fe  jz      short loc_18000D814
0x18000d800  mov     ecx, dword ptr [rbp+6C0h+var_730]
0x18000d803  lea     eax, [rcx-1]
0x18000d806  cmp     eax, 7Fh
0x18000d809  ja      short loc_18000D814
0x18000d80b  mov     [rsp+7C0h+var_758], rdx
0x18000d810  mov     [rsp+70h], ecx
0x18000d814  mov     rcx, [rdi+18h]
0x18000d818  mov     rax, [rcx]
0x18000d81b  mov     rax, [rax+30h]
0x18000d81f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d824  mov     qword ptr [rsp+7C0h+var_778], rax
0x18000d829  mov     rax, [rdi]
0x18000d82c  mov     qword ptr [rsp+7C0h+var_798+8], rax
0x18000d831  mov     eax, [rdi+8]
0x18000d834  mov     dword ptr [rsp+7C0h+var_788], eax
0x18000d838  mov     rbx, [r14+0A0h]
0x18000d83f  mov     qword ptr [rsp+7C0h+var_778+8], rbx
0x18000d844  mov     rax, [rdi+10h]
0x18000d848  mov     qword ptr [rsp+7C0h+var_768+8], rax
0x18000d84d  xor     eax, eax
0x18000d84f  mov     [rbp+6C0h+var_168], rax
0x18000d856  xorps   xmm0, xmm0
0x18000d859  movdqa  [rbp+6C0h+var_160], xmm0
0x18000d861  mov     [rbp+6C0h+var_150], rax
0x18000d868  mov     [rbp+6C0h+var_148], 0FA00h
0x18000d872  mov     r15d, 0C0h
0x18000d878  mov     r8d, r15d; Size
0x18000d87b  xor     edx, edx; Val
0x18000d87d  lea     rcx, [rbp+6C0h+var_138]; void *
0x18000d884  call    memset_0
0x18000d889  mov     [rbp+6C0h+var_78], 0
0x18000d894  xorps   xmm0, xmm0
0x18000d897  movdqa  [rbp+6C0h+var_70], xmm0
0x18000d89f  mov     [rbp+6C0h+var_60], 0
0x18000d8aa  mov     [rbp+6C0h+var_58], 0
0x18000d8b5  mov     [rbp+6C0h+var_50], 0
0x18000d8c0  mov     [rbp+6C0h+var_48], 0
0x18000d8cb  movdqa  [rbp+6C0h+var_40], xmm0
0x18000d8d3  movaps  xmm1, [rsp+7C0h+var_798+8]
0x18000d8d8  movaps  [rbp+6C0h+var_1B0], xmm1
0x18000d8df  movaps  xmm0, [rsp+7C0h+var_788+8]
0x18000d8e4  movaps  [rbp+6C0h+var_1A0], xmm0
0x18000d8eb  movaps  xmm1, [rsp+7C0h+var_778+8]
0x18000d8f0  movaps  [rbp+6C0h+var_190], xmm1
0x18000d8f7  movaps  xmm0, [rsp+7C0h+var_768+8]
0x18000d8fc  movaps  [rbp+6C0h+var_180], xmm0
0x18000d903  movsd   xmm1, qword ptr [rsp+70h]
0x18000d909  movsd   [rbp+6C0h+var_170], xmm1
0x18000d911  mov     qword ptr [rbp+6C0h+var_190], rbx
0x18000d918  call    cs:__imp_GetTickCount64
0x18000d91e  mov     [rbp+6C0h+var_128], rax
0x18000d925  mov     eax, dword ptr [rbp+6C0h+var_1B0+8]
0x18000d92b  mov     [rbp+6C0h+var_120], rax
0x18000d932  mov     [rbp+6C0h+var_138], r15d
0x18000d939  mov     rax, 21217A646D702121h
0x18000d943  mov     [rbp+6C0h+var_130], rax
0x18000d94a  mov     [rbp+6C0h+var_134], 2
0x18000d954  mov     [rbp+6C0h+var_A8], 1
0x18000d95e  xorps   xmm0, xmm0
0x18000d961  movups  xmmword ptr [rbp+6C0h+var_1E0.BaseAddress], xmm0
0x18000d968  movups  xmmword ptr [rbp+6C0h+var_1E0.AllocationProtect], xmm0
0x18000d96f  movups  xmmword ptr [rbp+6C0h+var_1E0.State], xmm0
0x18000d976  lea     rcx, [rbp+6C0h+var_1B0]; this
0x18000d97d  call    ?Init@CompressedMemStream@CompressedStreamDump@@QEAA_NXZ; CompressedStreamDump::CompressedMemStream::Init(void)
0x18000d982  test    al, al
0x18000d984  jnz     short loc_18000D990
0x18000d986  mov     ebx, 80004005h
0x18000d98b  jmp     loc_18000DBE0
0x18000d990  mov     eax, 0FFFFFFFFh
0x18000d995  cmp     [r14+0A0h], rax
0x18000d99c  jbe     short loc_18000D9C1
0x18000d99e  mov     rcx, [rdi+28h]
0x18000d9a2  mov     rax, [rcx]
0x18000d9a5  lea     r8, aFullMemoryStre_0; "Full memory stream RVA overflowed"
0x18000d9ac  mov     edx, esi
0x18000d9ae  mov     rax, [rax+8]
0x18000d9b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9b7  mov     ebx, 80070057h
0x18000d9bc  jmp     loc_18000DBE0
0x18000d9c1  xor     esi, esi
0x18000d9c3  xor     ebx, ebx
0x18000d9c5  lea     r15d, [rsi+1]
0x18000d9c9  test    rsi, rsi
0x18000d9cc  jnz     short loc_18000D9D7
0x18000d9ce  test    rbx, rbx
0x18000d9d1  jnz     loc_18000DB12
0x18000d9d7  mov     rcx, rdi; struct _MINIDUMP_STATE *
0x18000d9da  call    ?GenCheckCancel@@YAHPEAU_MINIDUMP_STATE@@@Z; GenCheckCancel(_MINIDUMP_STATE *)
0x18000d9df  test    eax, eax
0x18000d9e1  jnz     loc_18000DBDB
0x18000d9e7  test    rbx, rbx
0x18000d9ea  jz      short loc_18000DA07
0x18000d9ec  cmp     rsi, rbx
0x18000d9ef  ja      short loc_18000DA07
0x18000d9f1  mov     [rbp+6C0h+var_1E0.BaseAddress], rsi
0x18000d9f8  sub     rbx, rsi
0x18000d9fb  inc     rbx
0x18000d9fe  mov     [rbp+6C0h+var_1E0.RegionSize], rbx
0x18000da05  jmp     short loc_18000DA3F
0x18000da07  mov     rcx, [rdi+10h]
0x18000da0b  mov     rax, [rcx]
0x18000da0e  lea     r9, [rbp+6C0h+var_1E0]
0x18000da15  mov     r8, rsi
0x18000da18  mov     rdx, [rdi]
0x18000da1b  mov     rax, [rax+0F8h]
0x18000da22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da27  mov     ebx, eax
0x18000da29  test    eax, eax
0x18000da2b  jnz     loc_18000DAE2
0x18000da31  mov     rbx, [rbp+6C0h+var_1E0.RegionSize]
0x18000da38  mov     rsi, [rbp+6C0h+var_1E0.BaseAddress]
0x18000da3f  add     rsi, rbx
0x18000da42  lea     rbx, [rsi-1]
0x18000da46  mov     eax, [rbp+6C0h+var_1E0.Protect]
0x18000da4c  bt      eax, 8
0x18000da50  jb      loc_18000D9C9
0x18000da56  test    al, 1
0x18000da58  jnz     loc_18000D9C9
0x18000da5e  test    [rbp+6C0h+var_1E0.State], 10000h
0x18000da68  jnz     loc_18000D9C9
0x18000da6e  test    [rbp+6C0h+var_1E0.State], 2000h
0x18000da78  jnz     loc_18000D9C9
0x18000da7e  test    dword ptr [rdi+38h], 1000000h
0x18000da85  jz      short loc_18000DA91
0x18000da87  bt      eax, 0Ah
0x18000da8b  jb      loc_18000D9C9
0x18000da91  test    r15d, r15d
0x18000da94  jz      short loc_18000DAC2
0x18000da96  lea     rdx, [rbp+6C0h+var_1E0]; struct _MINIDUMP_MEMORY_INFO *
0x18000da9d  mov     rcx, rdi; struct _MINIDUMP_STATE *
0x18000daa0  call    ?FilterVmRegion@@YAHPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_MEMORY_INFO@@@Z; FilterVmRegion(_MINIDUMP_STATE *,_MINIDUMP_MEMORY_INFO *)
0x18000daa5  mov     r15d, eax
0x18000daa8  mov     rdx, [rbp+6C0h+var_1E0.RegionSize]
0x18000daaf  test    rdx, rdx
0x18000dab2  jz      loc_18000D9C9
0x18000dab8  mov     rsi, [rbp+6C0h+var_1E0.BaseAddress]
0x18000dabf  add     rsi, rdx
0x18000dac2  lea     rdx, [rbp+6C0h+var_1E0]; struct _MINIDUMP_MEMORY_INFO *
0x18000dac9  lea     rcx, [rbp+6C0h+var_1B0]; this
0x18000dad0  call    ?AddMemoryRegion@CompressedMemStream@CompressedStreamDump@@QEAA_NAEAU_MINIDUMP_MEMORY_INFO@@@Z; CompressedStreamDump::CompressedMemStream::AddMemoryRegion(_MINIDUMP_MEMORY_INFO &)
0x18000dad5  test    al, al
0x18000dad7  jnz     loc_18000D9C9
0x18000dadd  jmp     loc_18000D986
0x18000dae2  cmp     ebx, 80004002h
0x18000dae8  jz      short loc_18000DB12
0x18000daea  mov     rcx, [rdi+28h]
0x18000daee  mov     rax, [rcx]
0x18000daf1  mov     [rsp+20h], ebx
0x18000daf5  mov     r9, rsi
0x18000daf8  lea     r8, aWritefullmemor_7; "WriteFullMemoryCompressed.QueryVirtual("...
0x18000daff  mov     edx, 4
0x18000db04  mov     rax, [rax+8]
0x18000db08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db0d  jmp     loc_18000DBE0
0x18000db12  lea     rcx, [rbp+6C0h+var_1B0]; this
0x18000db19  call    ?AppendCompressedMemoryStream@CompressedMemStream@CompressedStreamDump@@QEAA_NXZ; CompressedStreamDump::CompressedMemStream::AppendCompressedMemoryStream(void)
0x18000db1e  test    al, al
0x18000db20  jnz     short loc_18000DB43
0x18000db22  mov     rcx, [rdi+28h]
0x18000db26  mov     rax, [rcx]
0x18000db29  lea     r8, aAppendcompress_0; "AppendCompressedMemoryStream failed."
0x18000db30  mov     edx, 4
0x18000db35  mov     rax, [rax+8]
0x18000db39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db3e  jmp     loc_18000D986
0x18000db43  mov     eax, [rbp+6C0h+var_110]
0x18000db49  mov     [r14+68h], eax
0x18000db4d  mov     dword ptr [r14+6Ch], 0C0h
0x18000db55  mov     rbx, [rbp+6C0h+var_108]
0x18000db5c  add     rax, rbx
0x18000db5f  mov     [r14+0A0h], rax
0x18000db66  cmp     qword ptr [rdi+40h], 0
0x18000db6b  jz      short loc_18000DBBB
0x18000db6d  xor     edx, edx; Val
0x18000db6f  mov     r8d, 520h; Size
0x18000db75  lea     rcx, [rbp+6C0h+var_700]; void *
0x18000db79  call    memset_0
0x18000db7e  xorps   xmm0, xmm0
0x18000db81  xor     eax, eax
0x18000db83  movups  [rbp+6C0h+var_740], xmm0
0x18000db87  movups  [rbp+6C0h+var_730], xmm0
0x18000db8b  movups  [rbp+6C0h+var_720], xmm0
0x18000db8f  mov     [rbp+6C0h+var_710], eax
0x18000db92  mov     [rbp+6C0h+var_6F4], 16h
0x18000db99  mov     [rbp+6C0h+var_6F0], rbx
0x18000db9d  mov     ecx, [rbp+6C0h+var_F0]
0x18000dba3  mov     [rbp+6C0h+var_6E8], ecx
0x18000dba6  lea     r8, [rbp+6C0h+var_740]
0x18000dbaa  lea     rdx, [rbp+6C0h+var_700]
0x18000dbae  mov     rcx, [rdi+50h]
0x18000dbb2  mov     rax, [rdi+40h]
0x18000dbb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbbb  mov     rcx, [rdi+28h]
0x18000dbbf  mov     rax, [rcx]
0x18000dbc2  lea     r8, aAppendcompress_1; "AppendCompressedMemoryStream completed "...
0x18000dbc9  mov     edx, 1
0x18000dbce  mov     rax, [rax+8]
0x18000dbd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbd7  xor     ebx, ebx
0x18000dbd9  jmp     short loc_18000DBE0
0x18000dbdb  mov     ebx, 800704C7h
0x18000dbe0  mov     rcx, [rdi+28h]
0x18000dbe4  mov     rax, [rcx]
0x18000dbe7  lea     r9, aWritememorycom; "WriteMemoryCompressed"
0x18000dbee  lea     r8, aLsExit; "%ls exit."
0x18000dbf5  mov     edx, 1
0x18000dbfa  mov     rax, [rax+8]
0x18000dbfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc03  nop
0x18000dc04  lea     rcx, [rbp+6C0h+var_48]
0x18000dc0b  call    ??1?$vector@UMemoryBucket@@V?$allocator@UMemoryBucket@@@std@@@std@@QEAA@XZ; std::vector<MemoryBucket>::~vector<MemoryBucket>(void)
0x18000dc10  lea     rcx, [rbp+6C0h+var_78]
0x18000dc17  call    ??1?$vector@UMemoryBucket@@V?$allocator@UMemoryBucket@@@std@@@std@@QEAA@XZ; std::vector<MemoryBucket>::~vector<MemoryBucket>(void)
0x18000dc1c  lea     rcx, [rbp+6C0h+var_160]
0x18000dc23  call    ??1?$vector@UMemoryRegion@@V?$allocator@UMemoryRegion@@@std@@@std@@QEAA@XZ; std::vector<MemoryRegion>::~vector<MemoryRegion>(void)
0x18000dc28  mov     rdi, [rbp+6C0h+var_168]
0x18000dc2f  test    rdi, rdi
0x18000dc32  jz      short loc_18000DC49
0x18000dc34  mov     rcx, rdi; this
0x18000dc37  call    ??1DumpWriter@CompressedStreamDump@@QEAA@XZ; CompressedStreamDump::DumpWriter::~DumpWriter(void)
0x18000dc3c  mov     edx, 38h ; '8'; unsigned __int64
0x18000dc41  mov     rcx, rdi; void *
0x18000dc44  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000dc49  mov     eax, ebx
0x18000dc4b  mov     rcx, [rbp+6C0h+var_30]
0x18000dc52  xor     rcx, rsp; StackCookie
0x18000dc55  call    __security_check_cookie
0x18000dc5a  mov     rbx, [rsp+7C0h+arg_10]
0x18000dc62  add     rsp, 7A0h
0x18000dc69  pop     r15
0x18000dc6b  pop     r14
0x18000dc6d  pop     rdi
0x18000dc6e  pop     rsi
0x18000dc6f  pop     rbp
0x18000dc70  retn
```
