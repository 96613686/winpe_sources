# CTableManager::RemoveAll(void)

- ea: `0x180020d40`
- end: `0x180020dc2`
- name: `?RemoveAll@CTableManager@@UEAAJXZ`
- size: `130`
- prototype: `__int64 __fastcall(CTableManager *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180020d40`

## import_xrefs

- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x180020d8d`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x180020d8d`
- `ntdll!RtlDeleteElementGenericTableAvlEx` at `0x180020d76`
- `ntdll!RtlDeleteElementGenericTableAvlEx` at `0x180020d76`

## string_xrefs

- `0x180020d4d`: `CTableManager::RemoveAll`

## pseudocode

```c
__int64 __fastcall CTableManager::RemoveAll(CTableManager *this)
{
  unsigned int v2; // ebx
  _DWORD v4[18]; // [rsp+20h] [rbp-48h] BYREF
  PVOID RestartKey; // [rsp+70h] [rbp+8h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)v4, "CTableManager::RemoveAll", 390, 1);
  while ( 1 )
  {
    RestartKey = 0;
    RtlEnumerateGenericTableWithoutSplayingAvl((PRTL_AVL_TABLE)((char *)this + 40), &RestartKey);
    if ( !RestartKey )
      break;
    RtlDeleteElementGenericTableAvlEx((char *)this + 40, RestartKey);
  }
  *((_DWORD *)this + 36) = 1;
  v2 = v4[0];
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)v4);
  return v2;
}

```

## disassembly

```asm
0x180020d40  mov     [rsp+arg_8], rbx
0x180020d45  push    rdi
0x180020d46  sub     rsp, 60h
0x180020d4a  mov     rdi, rcx
0x180020d4d  lea     rdx, aCtablemanagerR; "CTableManager::RemoveAll"
0x180020d54  lea     rcx, [rsp+68h+var_48]; this
0x180020d59  mov     r9d, 1; unsigned __int16
0x180020d5f  mov     r8d, 186h; unsigned __int16
0x180020d65  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180020d6a  lea     rbx, [rdi+28h]
0x180020d6e  jmp     short loc_180020D7C
0x180020d70  mov     rdx, rax
0x180020d73  mov     rcx, rbx
0x180020d76  call    cs:__imp_RtlDeleteElementGenericTableAvlEx
0x180020d7c  lea     rdx, [rsp+68h+RestartKey]; RestartKey
0x180020d81  mov     [rsp+68h+RestartKey], 0
0x180020d8a  mov     rcx, rbx; Table
0x180020d8d  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x180020d93  mov     rax, [rsp+68h+RestartKey]
0x180020d98  test    rax, rax
0x180020d9b  jnz     short loc_180020D70
0x180020d9d  mov     dword ptr [rdi+90h], 1
0x180020da7  mov     ebx, [rsp+68h+var_48]
0x180020dab  lea     rcx, [rsp+68h+var_48]; this
0x180020db0  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180020db5  mov     eax, ebx
0x180020db7  mov     rbx, [rsp+68h+arg_8]
0x180020dbc  add     rsp, 60h
0x180020dc0  pop     rdi
0x180020dc1  retn
```
