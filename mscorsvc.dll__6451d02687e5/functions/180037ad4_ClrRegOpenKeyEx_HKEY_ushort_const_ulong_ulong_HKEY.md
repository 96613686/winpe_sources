# ClrRegOpenKeyEx(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)

- ea: `0x180037ad4`
- end: `0x180037c0d`
- name: `?ClrRegOpenKeyEx@@YAJPEAUHKEY__@@PEBGKKPEAPEAU1@@Z`
- size: `313`
- prototype: `LSTATUS __fastcall(HKEY, const unsigned __int16 *, __int64, REGSAM, HKEY *phkResult)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800036b0`
- `0x180016794`
- `0x180016a9c`
- `0x1800178f0`
- `0x1800251bc`

## callees

- `0x1800375ac`
- `0x18003784c`
- `0x180037ad4`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180037b92`
- `ADVAPI32!RegOpenKeyExW` at `0x180037bed`
- `ADVAPI32!RegOpenKeyExW` at `0x180037b92`
- `ADVAPI32!RegOpenKeyExW` at `0x180037bed`
- `KERNEL32!HeapFree` at `0x180037bca`
- `KERNEL32!HeapFree` at `0x180037bca`
- `KERNEL32!GetProcessHeap` at `0x180037bb5`
- `KERNEL32!GetProcessHeap` at `0x180037bb5`

## pseudocode

```c
LSTATUS __fastcall ClrRegOpenKeyEx(HKEY a1, const unsigned __int16 *a2, __int64 a3, REGSAM a4, HKEY *phkResult)
{
  LSTATUS result; // eax
  LSTATUS v9; // edi
  int v10; // eax
  const WCHAR *v11; // rdx
  void *v12; // rbx
  HANDLE ProcessHeap; // rax
  LPVOID lpMem; // [rsp+40h] [rbp-10h] BYREF
  int v15; // [rsp+48h] [rbp-8h]

  if ( !byte_180070040 )
  {
    result = ParseRegistryRootConfigValue();
    if ( result )
      return result;
    byte_180070040 = 1;
  }
  if ( !qword_180070038 )
    return RegOpenKeyExW(a1, a2, 0, a4, phkResult);
  v15 = 0;
  lpMem = 0;
  v9 = RedirectKey(a4, a1, a2, (unsigned __int16 **)&lpMem);
  v10 = v15;
  v11 = (const WCHAR *)lpMem;
  if ( lpMem )
    v10 = 1;
  v15 = v10;
  if ( !v9 )
  {
    if ( !lpMem )
      v11 = a2;
    v9 = RegOpenKeyExW(a1, v11, 0, a4, phkResult);
  }
  if ( v15 )
  {
    v12 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
      }
      HeapFree(ProcessHeap, 0, v12);
    }
    v15 = 0;
  }
  return v9;
}

```

## disassembly

```asm
0x180037ad4  mov     [rsp-18h+arg_0], rbx
0x180037ad9  mov     [rsp-18h+arg_8], rsi
0x180037ade  mov     [rsp-18h+arg_10], rdi
0x180037ae3  push    rbp
0x180037ae4  push    r12
0x180037ae6  push    r14
0x180037ae8  mov     rbp, rsp
0x180037aeb  sub     rsp, 50h
0x180037aef  mov     ebx, r9d
0x180037af2  mov     rsi, rdx
0x180037af5  mov     r14, rcx
0x180037af8  and     [rbp+var_20], 0
0x180037afc  mov     al, cs:byte_180070040
0x180037b02  mov     r12d, 1
0x180037b08  test    al, al
0x180037b0a  jnz     short loc_180037B20
0x180037b0c  call    ?ParseRegistryRootConfigValue@@YAJXZ; ParseRegistryRootConfigValue(void)
0x180037b11  test    eax, eax
0x180037b13  jnz     loc_180037BF3
0x180037b19  mov     cs:byte_180070040, r12b
0x180037b20  cmp     cs:qword_180070038, 0
0x180037b28  jz      loc_180037BD8
0x180037b2e  and     [rbp+lpMem], 0
0x180037b33  and     [rbp+var_8], 0
0x180037b37  lea     rax, [rbp+lpMem]
0x180037b3b  mov     [rbp+var_18], rax
0x180037b3f  and     [rbp+lpMem], 0
0x180037b44  mov     [rbp+var_20], r12d
0x180037b48  lea     r9, [rbp+lpMem]; unsigned __int16 **
0x180037b4c  mov     r8, rsi; unsigned __int16 *
0x180037b4f  mov     rdx, r14; HKEY
0x180037b52  mov     ecx, ebx; unsigned int
0x180037b54  call    ?RedirectKey@@YAJKPEAUHKEY__@@PEBGPEAPEAG@Z; RedirectKey(ulong,HKEY__ *,ushort const *,ushort * *)
0x180037b59  mov     edi, eax
0x180037b5b  mov     eax, r12d
0x180037b5e  and     eax, 0FFFFFFFEh
0x180037b61  mov     [rbp+var_20], eax
0x180037b64  mov     eax, [rbp+var_8]
0x180037b67  mov     rdx, [rbp+lpMem]
0x180037b6b  test    rdx, rdx
0x180037b6e  cmovnz  eax, r12d
0x180037b72  mov     [rbp+var_8], eax
0x180037b75  test    edi, edi
0x180037b77  jnz     short loc_180037B9A
0x180037b79  test    rdx, rdx
0x180037b7c  cmovz   rdx, rsi; lpSubKey
0x180037b80  mov     rax, [rbp+arg_20]
0x180037b84  mov     [rsp+50h+phkResult], rax; phkResult
0x180037b89  mov     r9d, ebx; samDesired
0x180037b8c  xor     r8d, r8d; ulOptions
0x180037b8f  mov     rcx, r14; hKey
0x180037b92  call    cs:__imp_RegOpenKeyExW
0x180037b98  mov     edi, eax
0x180037b9a  cmp     [rbp+var_8], 0
0x180037b9e  jz      short loc_180037BD4
0x180037ba0  mov     rbx, [rbp+lpMem]
0x180037ba4  test    rbx, rbx
0x180037ba7  jz      short loc_180037BD0
0x180037ba9  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180037bb0  test    rax, rax
0x180037bb3  jnz     short loc_180037BC2
0x180037bb5  call    cs:__imp_GetProcessHeap
0x180037bbb  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180037bc2  mov     r8, rbx; lpMem
0x180037bc5  xor     edx, edx; dwFlags
0x180037bc7  mov     rcx, rax; hHeap
0x180037bca  call    cs:__imp_HeapFree
0x180037bd0  and     [rbp+var_8], 0
0x180037bd4  mov     eax, edi
0x180037bd6  jmp     short loc_180037BF3
0x180037bd8  mov     rax, [rbp+arg_20]
0x180037bdc  mov     [rsp+50h+phkResult], rax; phkResult
0x180037be1  mov     r9d, ebx; samDesired
0x180037be4  xor     r8d, r8d; ulOptions
0x180037be7  mov     rdx, rsi; lpSubKey
0x180037bea  mov     rcx, r14; hKey
0x180037bed  call    cs:__imp_RegOpenKeyExW
0x180037bf3  lea     r11, [rsp+50h+var_s0]
0x180037bf8  mov     rbx, [r11+20h]
0x180037bfc  mov     rsi, [r11+28h]
0x180037c00  mov     rdi, [r11+30h]
0x180037c04  mov     rsp, r11
0x180037c07  pop     r14
0x180037c09  pop     r12
0x180037c0b  pop     rbp
0x180037c0c  retn
```
