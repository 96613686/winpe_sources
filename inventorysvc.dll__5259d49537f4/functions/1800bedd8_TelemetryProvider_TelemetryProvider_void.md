# TelemetryProvider::~TelemetryProvider(void)

- ea: `0x1800bedd8`
- end: `0x1800beec7`
- name: `??1TelemetryProvider@@QEAA@XZ`
- size: `239`
- prototype: `void __fastcall(TelemetryProvider *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180020764`
- `0x18002099c`
- `0x180022e5c`
- `0x1800be9e8`

## callees

- `0x1800bedd8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800beded`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bee11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bee36`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bee5b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800beded`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bee11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bee36`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bee5b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bedfb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bee1f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bee44`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bee69`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bedfb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bee1f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bee44`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bee69`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800beea4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800beea4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bee80`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800beeae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bee80`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800beeae`

## pseudocode

```c
void __fastcall TelemetryProvider::~TelemetryProvider(TelemetryProvider *this)
{
  void *v1; // rdi
  HANDLE ProcessHeap; // rax
  void *v4; // rdi
  HANDLE v5; // rax
  void *v6; // rdi
  HANDLE v7; // rax
  void *v8; // rdi
  HANDLE v9; // rax
  HKEY v10; // rcx
  HKEY v11; // rcx

  v1 = *(void **)this;
  if ( *(_QWORD *)this )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
    *(_QWORD *)this = 0;
  }
  v4 = (void *)*((_QWORD *)this + 1);
  if ( v4 )
  {
    v5 = GetProcessHeap();
    HeapFree(v5, 0, v4);
    *((_QWORD *)this + 1) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 2);
  if ( v6 )
  {
    v7 = GetProcessHeap();
    HeapFree(v7, 0, v6);
    *((_QWORD *)this + 2) = 0;
  }
  v8 = (void *)*((_QWORD *)this + 3);
  if ( v8 )
  {
    v9 = GetProcessHeap();
    HeapFree(v9, 0, v8);
    *((_QWORD *)this + 3) = 0;
  }
  v10 = (HKEY)*((_QWORD *)this + 4);
  if ( v10 )
  {
    RegCloseKey(v10);
    *((_QWORD *)this + 4) = 0;
  }
  v11 = (HKEY)*((_QWORD *)this + 5);
  if ( v11 )
  {
    if ( *((_BYTE *)this + 52) )
      RegDeleteValueW(v11, L"Pending");
    RegCloseKey(*((HKEY *)this + 5));
    *((_QWORD *)this + 5) = 0;
  }
}

```

## disassembly

```asm
0x1800bedd8  mov     [rsp+arg_0], rbx
0x1800beddd  push    rdi
0x1800bedde  sub     rsp, 20h
0x1800bede2  mov     rdi, [rcx]
0x1800bede5  mov     rbx, rcx
0x1800bede8  test    rdi, rdi
0x1800bedeb  jz      short loc_1800BEE08
0x1800beded  call    cs:__imp_GetProcessHeap
0x1800bedf3  mov     r8, rdi; lpMem
0x1800bedf6  xor     edx, edx; dwFlags
0x1800bedf8  mov     rcx, rax; hHeap
0x1800bedfb  call    cs:__imp_HeapFree
0x1800bee01  mov     qword ptr [rbx], 0
0x1800bee08  mov     rdi, [rbx+8]
0x1800bee0c  test    rdi, rdi
0x1800bee0f  jz      short loc_1800BEE2D
0x1800bee11  call    cs:__imp_GetProcessHeap
0x1800bee17  mov     r8, rdi; lpMem
0x1800bee1a  xor     edx, edx; dwFlags
0x1800bee1c  mov     rcx, rax; hHeap
0x1800bee1f  call    cs:__imp_HeapFree
0x1800bee25  mov     qword ptr [rbx+8], 0
0x1800bee2d  mov     rdi, [rbx+10h]
0x1800bee31  test    rdi, rdi
0x1800bee34  jz      short loc_1800BEE52
0x1800bee36  call    cs:__imp_GetProcessHeap
0x1800bee3c  mov     r8, rdi; lpMem
0x1800bee3f  xor     edx, edx; dwFlags
0x1800bee41  mov     rcx, rax; hHeap
0x1800bee44  call    cs:__imp_HeapFree
0x1800bee4a  mov     qword ptr [rbx+10h], 0
0x1800bee52  mov     rdi, [rbx+18h]
0x1800bee56  test    rdi, rdi
0x1800bee59  jz      short loc_1800BEE77
0x1800bee5b  call    cs:__imp_GetProcessHeap
0x1800bee61  mov     r8, rdi; lpMem
0x1800bee64  xor     edx, edx; dwFlags
0x1800bee66  mov     rcx, rax; hHeap
0x1800bee69  call    cs:__imp_HeapFree
0x1800bee6f  mov     qword ptr [rbx+18h], 0
0x1800bee77  mov     rcx, [rbx+20h]; hKey
0x1800bee7b  test    rcx, rcx
0x1800bee7e  jz      short loc_1800BEE8E
0x1800bee80  call    cs:__imp_RegCloseKey
0x1800bee86  mov     qword ptr [rbx+20h], 0
0x1800bee8e  mov     rcx, [rbx+28h]; hKey
0x1800bee92  test    rcx, rcx
0x1800bee95  jz      short loc_1800BEEBC
0x1800bee97  cmp     byte ptr [rbx+34h], 0
0x1800bee9b  jz      short loc_1800BEEAA
0x1800bee9d  lea     rdx, ValueName; "Pending"
0x1800beea4  call    cs:__imp_RegDeleteValueW
0x1800beeaa  mov     rcx, [rbx+28h]; hKey
0x1800beeae  call    cs:__imp_RegCloseKey
0x1800beeb4  mov     qword ptr [rbx+28h], 0
0x1800beebc  mov     rbx, [rsp+28h+arg_0]
0x1800beec1  add     rsp, 20h
0x1800beec5  pop     rdi
0x1800beec6  retn
```
