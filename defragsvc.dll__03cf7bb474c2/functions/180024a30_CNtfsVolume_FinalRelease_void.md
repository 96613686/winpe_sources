# CNtfsVolume::FinalRelease(void)

- ea: `0x180024a30`
- end: `0x180024af4`
- name: `?FinalRelease@CNtfsVolume@@QEAAJXZ`
- size: `196`
- prototype: `__int64 __fastcall(CNtfsVolume *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800249fc`
- `0x18006228c`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180024a30`
- `0x180024afc`
- `0x180038f18`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024a6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024acd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024a6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024acd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CNtfsVolume::FinalRelease(CNtfsVolume *this)
{
  _QWORD *v2; // rdi
  void *v3; // rcx
  void *v4; // rcx
  CSxStringList *v5; // rcx
  unsigned int v6; // ebx
  _DWORD v8[18]; // [rsp+20h] [rbp-48h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)v8, "CNtfsVolume::FinalRelease", 383, 1);
  v2 = (_QWORD *)*((_QWORD *)this + 72);
  while ( v2 )
  {
    v3 = v2;
    v2 = (_QWORD *)v2[1];
    CoTaskMemFree(v3);
  }
  *((_QWORD *)this + 72) = 0;
  v4 = (void *)*((_QWORD *)this + 51);
  if ( v4 )
  {
    CoTaskMemFree(v4);
    *((_QWORD *)this + 51) = 0;
  }
  v5 = (CSxStringList *)*((_QWORD *)this + 80);
  if ( v5 )
  {
    CSxStringList::Release(v5);
    *((_QWORD *)this + 80) = 0;
  }
  *((_QWORD *)this + 79) = 0;
  *((_DWORD *)this + 156) = 0;
  CVolume::_DestroyVars(this);
  v6 = v8[0];
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)v8);
  return v6;
}

```

## disassembly

```asm
0x180024a30  mov     [rsp+arg_0], rbx
0x180024a35  push    rdi
0x180024a36  sub     rsp, 60h
0x180024a3a  mov     rbx, rcx
0x180024a3d  mov     r9d, 1; unsigned __int16
0x180024a43  mov     r8d, 17Fh; unsigned __int16
0x180024a49  lea     rdx, aCntfsvolumeFin_0; "CNtfsVolume::FinalRelease"
0x180024a50  lea     rcx, [rsp+68h+var_48]; this
0x180024a55  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180024a5a  nop
0x180024a5b  mov     rdi, [rbx+240h]
0x180024a62  jmp     short loc_180024A71
0x180024a64  mov     rcx, rdi; pv
0x180024a67  mov     rdi, [rdi+8]
0x180024a6b  call    cs:__imp_CoTaskMemFree
0x180024a71  test    rdi, rdi
0x180024a74  jnz     short loc_180024A64
0x180024a76  mov     [rbx+240h], rdi
0x180024a7d  mov     rcx, [rbx+198h]; pv
0x180024a84  test    rcx, rcx
0x180024a87  jnz     short loc_180024ACD
0x180024a89  mov     rcx, [rbx+280h]; this
0x180024a90  test    rcx, rcx
0x180024a93  jnz     short loc_180024AE1
0x180024a95  mov     qword ptr [rbx+278h], 0
0x180024aa0  mov     dword ptr [rbx+270h], 0
0x180024aaa  mov     rcx, rbx; this
0x180024aad  call    ?_DestroyVars@CVolume@@IEAAJXZ; CVolume::_DestroyVars(void)
0x180024ab2  mov     ebx, [rsp+68h+var_48]
0x180024ab6  lea     rcx, [rsp+68h+var_48]; this
0x180024abb  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180024ac0  mov     eax, ebx
0x180024ac2  mov     rbx, [rsp+68h+arg_0]
0x180024ac7  add     rsp, 60h
0x180024acb  pop     rdi
0x180024acc  retn
0x180024acd  call    cs:__imp_CoTaskMemFree
0x180024ad3  nop
0x180024ad4  mov     qword ptr [rbx+198h], 0
0x180024adf  jmp     short loc_180024A89
0x180024ae1  call    ?Release@CSxStringList@@QEAAKXZ; CSxStringList::Release(void)
0x180024ae6  mov     qword ptr [rbx+280h], 0
0x180024af1  jmp     short loc_180024A95
```
