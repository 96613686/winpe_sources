# TBinFileMappingCache::GetFileMappingPointer(ushort const *,FixedTableHeap const * &)

- ea: `0x180026500`
- end: `0x1800265da`
- name: `?GetFileMappingPointer@TBinFileMappingCache@@SAXPEBGAEAPEBVFixedTableHeap@@@Z`
- size: `218`
- prototype: `void __fastcall(const unsigned __int16 *, const struct FixedTableHeap **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800289c0`

## callees

- `0x1800117b4`
- `0x180025bdc`
- `0x180026500`
- `0x180028868`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180026545`
- `msvcrt!_wcsicmp` at `0x180026545`
- `ole32!CoTaskMemAlloc` at `0x18002655a`
- `ole32!CoTaskMemAlloc` at `0x18002655a`

## pseudocode

```c
void __fastcall TBinFileMappingCache::GetFileMappingPointer(
        const unsigned __int16 *a1,
        const struct FixedTableHeap **a2)
{
  struct TBinFileMappingCache *v2; // rbx
  struct TBinFileMappingCache *v5; // rax
  unsigned int v6; // edx
  const struct FixedTableHeap *v7; // rax
  int v8; // [rsp+20h] [rbp-18h] BYREF
  _RTL_CRITICAL_SECTION *v9; // [rsp+28h] [rbp-10h]

  v2 = TBinFileMappingCache::m_pFirst;
  *a2 = (const struct FixedTableHeap *)&g_aFixedTableHeap;
  v8 = 0;
  v9 = &TBinFileMappingCache::m_CriticalSection;
  while ( v2 )
  {
    if ( !_wcsicmp(a1, *(const wchar_t **)v2) )
      goto LABEL_8;
    v2 = (struct TBinFileMappingCache *)*((_QWORD *)v2 + 6);
  }
  v5 = (struct TBinFileMappingCache *)CoTaskMemAlloc(0x38u);
  v2 = v5;
  if ( !v5 )
    goto LABEL_9;
  *(_QWORD *)v5 = 0;
  *((_QWORD *)v5 + 1) = 0;
  *((_QWORD *)v5 + 2) = 0;
  *((_QWORD *)v5 + 3) = 0;
  *((_DWORD *)v5 + 8) = 0;
  *((_DWORD *)v5 + 10) = 0;
  *((_QWORD *)v5 + 6) = 0;
  if ( (int)TBinFileMappingCache::Init(v5, a1) < 0 )
  {
    TBinFileMappingCache::`scalar deleting destructor'(v2, v6);
    goto LABEL_9;
  }
LABEL_8:
  v7 = (const struct FixedTableHeap *)*((_QWORD *)v2 + 3);
  ++*((_DWORD *)v2 + 10);
  *a2 = v7;
LABEL_9:
  CSafeLock::~CSafeLock((CSafeLock *)&v8);
}

```

## disassembly

```asm
0x180026500  mov     [rsp+arg_0], rbx
0x180026505  mov     [rsp+arg_8], rsi
0x18002650a  push    rdi
0x18002650b  sub     rsp, 30h
0x18002650f  mov     rbx, cs:?m_pFirst@TBinFileMappingCache@@0PEAV1@EA; TBinFileMappingCache * TBinFileMappingCache::m_pFirst
0x180026516  lea     rax, ?g_aFixedTableHeap@@3PAKA; ulong near * g_aFixedTableHeap
0x18002651d  mov     [rdx], rax
0x180026520  mov     rdi, rdx
0x180026523  lea     rax, ?m_CriticalSection@TBinFileMappingCache@@0VCSafeAutoCriticalSection@@A; CSafeAutoCriticalSection TBinFileMappingCache::m_CriticalSection
0x18002652a  mov     [rsp+38h+var_18], 0
0x180026532  mov     [rsp+38h+var_10], rax
0x180026537  mov     rsi, rcx
0x18002653a  test    rbx, rbx
0x18002653d  jz      short loc_180026555
0x18002653f  mov     rdx, [rbx]; String2
0x180026542  mov     rcx, rsi; String1
0x180026545  call    cs:__imp__wcsicmp
0x18002654b  test    eax, eax
0x18002654d  jz      short loc_1800265B6
0x18002654f  mov     rbx, [rbx+30h]
0x180026553  jmp     short loc_18002653A
0x180026555  mov     ecx, 38h ; '8'; cb
0x18002655a  call    cs:__imp_CoTaskMemAlloc
0x180026560  mov     rbx, rax
0x180026563  test    rax, rax
0x180026566  jz      short loc_1800265C0
0x180026568  mov     qword ptr [rax], 0
0x18002656f  mov     rdx, rsi; unsigned __int16 *
0x180026572  mov     qword ptr [rax+8], 0
0x18002657a  mov     rcx, rax; this
0x18002657d  mov     qword ptr [rax+10h], 0
0x180026585  mov     qword ptr [rax+18h], 0
0x18002658d  mov     dword ptr [rax+20h], 0
0x180026594  mov     dword ptr [rax+28h], 0
0x18002659b  mov     qword ptr [rax+30h], 0
0x1800265a3  call    ?Init@TBinFileMappingCache@@AEAAJPEBG@Z; TBinFileMappingCache::Init(ushort const *)
0x1800265a8  test    eax, eax
0x1800265aa  jns     short loc_1800265B6
0x1800265ac  mov     rcx, rbx; this
0x1800265af  call    ??_GTBinFileMappingCache@@AEAAPEAXI@Z; TBinFileMappingCache::`scalar deleting destructor'(uint)
0x1800265b4  jmp     short loc_1800265C0
0x1800265b6  mov     rax, [rbx+18h]
0x1800265ba  inc     dword ptr [rbx+28h]
0x1800265bd  mov     [rdi], rax
0x1800265c0  lea     rcx, [rsp+38h+var_18]; this
0x1800265c5  call    ??1CSafeLock@@QEAA@XZ; CSafeLock::~CSafeLock(void)
0x1800265ca  mov     rbx, [rsp+38h+arg_0]
0x1800265cf  mov     rsi, [rsp+38h+arg_8]
0x1800265d4  add     rsp, 30h
0x1800265d8  pop     rdi
0x1800265d9  retn
```
