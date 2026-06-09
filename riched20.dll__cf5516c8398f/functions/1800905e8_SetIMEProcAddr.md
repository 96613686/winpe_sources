# SetIMEProcAddr

- ea: `0x1800905e8`
- end: `0x180090678`
- name: `SetIMEProcAddr`
- size: `144`
- prototype: ``
- caller_count: `18`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800525d4`
- `0x18008e4fc`
- `0x18008e588`
- `0x18008e6c8`
- `0x18008e754`
- `0x18008e7f8`
- `0x18008e89c`
- `0x18008e920`
- `0x18008e9ac`
- `0x18008ea30`
- `0x18008eac0`
- `0x18008eb50`
- `0x18008ebd0`
- `0x18008ec4c`
- `0x18008ecc8`
- `0x18008ed34`
- `0x18008edb0`
- `0x18008ee3c`

## callees

- `0x18008f8b0`
- `0x1800905e8`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180090606`
- `KERNEL32!EnterCriticalSection` at `0x180090606`
- `KERNEL32!LeaveCriticalSection` at `0x180090671`
- `KERNEL32!GetProcAddress` at `0x180090652`
- `KERNEL32!GetProcAddress` at `0x180090652`

## string_xrefs

- `0x180090634`: `imm32.dll`

## pseudocode

```c
void __fastcall SetIMEProcAddr(FARPROC *a1, int a2, const CHAR *a3)
{
  __int64 v6; // rdx
  unsigned int v7; // r8d
  HINSTANCE Library; // rax

  EnterCriticalSection(&g_CriticalSection);
  if ( !*a1 )
  {
    if ( a2 )
    {
      if ( a2 == 1 )
        hModule = (HMODULE)-1LL;
    }
    else
    {
      Library = qword_1800A44A8;
      if ( qword_1800A44A8
        || (Library = CW32System::LoadLibrary(L"imm32.dll", v6, v7), (qword_1800A44A8 = Library) != 0) )
      {
        *a1 = GetProcAddress(Library, a3);
      }
    }
  }
  LeaveCriticalSection(&g_CriticalSection);
}

```

## disassembly

```asm
0x1800905e8  mov     [rsp+arg_0], rbx
0x1800905ed  mov     [rsp+arg_8], rsi
0x1800905f2  push    rdi
0x1800905f3  sub     rsp, 20h
0x1800905f7  mov     rdi, rcx
0x1800905fa  mov     rsi, r8
0x1800905fd  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180090604  mov     ebx, edx
0x180090606  call    cs:__imp_EnterCriticalSection
0x18009060c  cmp     qword ptr [rdi], 0
0x180090610  jnz     short loc_18009065B
0x180090612  test    ebx, ebx
0x180090614  jz      short loc_180090628
0x180090616  cmp     ebx, 1
0x180090619  jnz     short loc_18009065B
0x18009061b  mov     cs:hModule, 0FFFFFFFFFFFFFFFFh
0x180090626  jmp     short loc_18009065B
0x180090628  mov     rax, cs:qword_1800A44A8
0x18009062f  test    rax, rax
0x180090632  jnz     short loc_18009064C
0x180090634  lea     rcx, aImm32Dll; "imm32.dll"
0x18009063b  call    ?LoadLibrary@CW32System@@SAPEAUHINSTANCE__@@PEBG@Z; CW32System::LoadLibrary(ushort const *)
0x180090640  mov     cs:qword_1800A44A8, rax
0x180090647  test    rax, rax
0x18009064a  jz      short loc_18009065B
0x18009064c  mov     rdx, rsi; lpProcName
0x18009064f  mov     rcx, rax; hModule
0x180090652  call    cs:__imp_GetProcAddress
0x180090658  mov     [rdi], rax
0x18009065b  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_CriticalSection
0x180090662  mov     rbx, [rsp+28h+arg_0]
0x180090667  mov     rsi, [rsp+28h+arg_8]
0x18009066c  add     rsp, 20h
0x180090670  pop     rdi
0x180090671  jmp     cs:__imp_LeaveCriticalSection
```
