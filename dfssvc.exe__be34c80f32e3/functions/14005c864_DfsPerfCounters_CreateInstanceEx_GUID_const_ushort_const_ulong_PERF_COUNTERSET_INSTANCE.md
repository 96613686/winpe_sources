# DfsPerfCounters::CreateInstanceEx(_GUID const *,ushort const *,ulong,_PERF_COUNTERSET_INSTANCE * &)

- ea: `0x14005c864`
- end: `0x14005c95a`
- name: `?CreateInstanceEx@DfsPerfCounters@@SAKPEBU_GUID@@PEBGKAEAPEAU_PERF_COUNTERSET_INSTANCE@@@Z`
- size: `246`
- prototype: `unsigned int __fastcall(LPCGUID CounterSetGuid, const unsigned __int16 *, unsigned int, struct _PERF_COUNTERSET_INSTANCE **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x14000a4f8`

## callees

- `0x140002a1c`
- `0x140040190`
- `0x14005c864`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005c928`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005c928`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x14005c914`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x14005c914`

## pseudocode

```c
__int64 __fastcall DfsPerfCounters::CreateInstanceEx(
        LPCGUID CounterSetGuid,
        const unsigned __int16 *a2,
        __int64 a3,
        struct _PERF_COUNTERSET_INSTANCE **a4)
{
  DWORD LastError; // ebx
  __int64 v7; // rdi
  const WCHAR *v9; // rax
  WCHAR *v10; // rsi
  __int64 v11; // r8
  __int64 v12; // r10
  unsigned __int16 v13; // r9
  struct _PERF_COUNTERSET_INSTANCE *Instance; // rax

  LastError = 0;
  v7 = -1;
  do
    ++v7;
  while ( a2[v7] );
  v9 = (const WCHAR *)operator new[](saturated_mul((unsigned int)(v7 + 1), 2u));
  v10 = (WCHAR *)v9;
  if ( v9 )
  {
    if ( (_DWORD)v7 )
    {
      v11 = 0;
      v12 = (unsigned int)v7;
      do
      {
        v13 = a2[v11];
        if ( v13 == 35 || a2[v11] == 40 || a2[v11] == 41 || a2[v11] == 47 || a2[v11] == 92 )
          v13 = 46;
        v9[v11++] = v13;
        --v12;
      }
      while ( v12 );
    }
    v9[(unsigned int)v7] = 0;
    Instance = PerfCreateInstance(DFSN_ServerService, CounterSetGuid, v9, 0);
    *a4 = Instance;
    if ( !Instance )
      LastError = GetLastError();
    DfsDomainV2DeallocateShashData(v10);
  }
  else
  {
    return 8;
  }
  return LastError;
}

```

## disassembly

```asm
0x14005c864  mov     [rsp+arg_0], rbx
0x14005c869  mov     [rsp+arg_8], rbp
0x14005c86e  mov     [rsp+arg_10], rsi
0x14005c873  push    rdi
0x14005c874  push    r14
0x14005c876  push    r15
0x14005c878  sub     rsp, 20h
0x14005c87c  xor     ebx, ebx
0x14005c87e  mov     r14, r9
0x14005c881  or      r8, 0FFFFFFFFFFFFFFFFh
0x14005c885  mov     rbp, rdx
0x14005c888  mov     rdi, r8
0x14005c88b  mov     r15, rcx
0x14005c88e  inc     rdi
0x14005c891  cmp     [rdx+rdi*2], bx
0x14005c895  jnz     short loc_14005C88E
0x14005c897  lea     ecx, [rdi+1]
0x14005c89a  mov     eax, 2
0x14005c89f  mul     rcx
0x14005c8a2  cmovo   rax, r8
0x14005c8a6  mov     rcx, rax; unsigned __int64
0x14005c8a9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14005c8ae  mov     rsi, rax
0x14005c8b1  test    rax, rax
0x14005c8b4  jnz     short loc_14005C8BE
0x14005c8b6  lea     ebx, [rax+8]
0x14005c8b9  jmp     loc_14005C93E
0x14005c8be  mov     edx, edi
0x14005c8c0  test    edi, edi
0x14005c8c2  jz      short loc_14005C900
0x14005c8c4  mov     r8, rbx
0x14005c8c7  mov     r10d, edx
0x14005c8ca  movzx   r9d, word ptr [r8+rbp]
0x14005c8cf  mov     ecx, r9d
0x14005c8d2  sub     ecx, 23h ; '#'
0x14005c8d5  jz      short loc_14005C8EB
0x14005c8d7  sub     ecx, 5
0x14005c8da  jz      short loc_14005C8EB
0x14005c8dc  sub     ecx, 1
0x14005c8df  jz      short loc_14005C8EB
0x14005c8e1  sub     ecx, 6
0x14005c8e4  jz      short loc_14005C8EB
0x14005c8e6  cmp     ecx, 2Dh ; '-'
0x14005c8e9  jnz     short loc_14005C8F1
0x14005c8eb  mov     r9d, 2Eh ; '.'
0x14005c8f1  mov     [r8+rax], r9w
0x14005c8f6  add     r8, 2
0x14005c8fa  sub     r10, 1
0x14005c8fe  jnz     short loc_14005C8CA
0x14005c900  mov     [rax+rdx*2], bx
0x14005c904  xor     r9d, r9d; Id
0x14005c907  mov     rcx, cs:DFSN_ServerService; ProviderHandle
0x14005c90e  mov     rdx, r15; CounterSetGuid
0x14005c911  mov     r8, rsi; Name
0x14005c914  call    cs:__imp_PerfCreateInstance
0x14005c91b  nop     dword ptr [rax+rax+00h]
0x14005c920  mov     [r14], rax
0x14005c923  test    rax, rax
0x14005c926  jnz     short loc_14005C936
0x14005c928  call    cs:__imp_GetLastError
0x14005c92f  nop     dword ptr [rax+rax+00h]
0x14005c934  mov     ebx, eax
0x14005c936  mov     rcx, rsi; Block
0x14005c939  call    ?DfsDomainV2DeallocateShashData@@YAXPEAX@Z; DfsDomainV2DeallocateShashData(void *)
0x14005c93e  mov     rbp, [rsp+38h+arg_8]
0x14005c943  mov     eax, ebx
0x14005c945  mov     rbx, [rsp+38h+arg_0]
0x14005c94a  mov     rsi, [rsp+38h+arg_10]
0x14005c94f  add     rsp, 20h
0x14005c953  pop     r15
0x14005c955  pop     r14
0x14005c957  pop     rdi
0x14005c958  retn
```
