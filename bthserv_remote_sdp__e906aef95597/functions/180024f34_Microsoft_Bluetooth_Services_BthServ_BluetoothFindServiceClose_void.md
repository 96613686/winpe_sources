# Microsoft::Bluetooth::Services::BthServ::BluetoothFindServiceClose(void *)

- ea: `0x180024f34`
- end: `0x180024fc0`
- name: `?BluetoothFindServiceClose@BthServ@Services@Bluetooth@Microsoft@@YAHPEAX@Z`
- size: `140`
- prototype: `__int64 __fastcall(void **this, void *)`
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180025648`
- `0x180026650`
- `0x180026808`
- `0x180026dec`
- `0x180027ea8`

## callees

- `0x180024f34`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024f55`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024f75`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024f55`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024f75`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024f69`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024f89`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024f69`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024f89`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024fa1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024fa1`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Services::BthServ::BluetoothFindServiceClose(void **this, void *a2)
{
  unsigned int v2; // ebx
  void *v4; // rsi
  HANDLE ProcessHeap; // rax
  HANDLE v6; // rax

  v2 = 0;
  if ( this )
  {
    v4 = *this;
    if ( *this )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v4);
    }
    v6 = GetProcessHeap();
    HeapFree(v6, 0, this);
    return 1;
  }
  else
  {
    SetLastError(6u);
  }
  return v2;
}

```

## disassembly

```asm
0x180024f34  mov     [rsp+arg_0], rbx
0x180024f39  mov     [rsp+arg_8], rsi
0x180024f3e  push    rdi
0x180024f3f  sub     rsp, 20h
0x180024f43  xor     ebx, ebx
0x180024f45  mov     rdi, rcx
0x180024f48  test    rcx, rcx
0x180024f4b  jz      short loc_180024F9C
0x180024f4d  mov     rsi, [rcx]
0x180024f50  test    rsi, rsi
0x180024f53  jz      short loc_180024F75
0x180024f55  call    cs:__imp_GetProcessHeap
0x180024f5c  nop     dword ptr [rax+rax+00h]
0x180024f61  mov     r8, rsi; lpMem
0x180024f64  xor     edx, edx; dwFlags
0x180024f66  mov     rcx, rax; hHeap
0x180024f69  call    cs:__imp_HeapFree
0x180024f70  nop     dword ptr [rax+rax+00h]
0x180024f75  call    cs:__imp_GetProcessHeap
0x180024f7c  nop     dword ptr [rax+rax+00h]
0x180024f81  mov     r8, rdi; lpMem
0x180024f84  xor     edx, edx; dwFlags
0x180024f86  mov     rcx, rax; hHeap
0x180024f89  call    cs:__imp_HeapFree
0x180024f90  nop     dword ptr [rax+rax+00h]
0x180024f95  mov     ebx, 1
0x180024f9a  jmp     short loc_180024FAD
0x180024f9c  mov     ecx, 6; dwErrCode
0x180024fa1  call    cs:__imp_SetLastError
0x180024fa8  nop     dword ptr [rax+rax+00h]
0x180024fad  mov     rsi, [rsp+28h+arg_8]
0x180024fb2  mov     eax, ebx
0x180024fb4  mov     rbx, [rsp+28h+arg_0]
0x180024fb9  add     rsp, 20h
0x180024fbd  pop     rdi
0x180024fbe  retn
```
