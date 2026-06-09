# Enrollment::set_Discovery(HKEY__ *,ushort *)

- ea: `0x18003f9b0`
- end: `0x18003faf9`
- name: `?set_Discovery@Enrollment@@QEAAJPEAUHKEY__@@PEAG@Z`
- size: `329`
- prototype: `int(Enrollment *__hidden this, HKEY, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003bf04`

## callees

- `0x18003f9b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003fa43`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003fa43`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003fabd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003fabd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003fa2f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003faa9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003fa2f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003faa9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003f9ff`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003fa88`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003f9ff`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003fa88`

## string_xrefs

- `0x18003f9d9`: `DiscoveryServiceFullURL`
- `0x18003fa6d`: `DiscoveryServiceFullURL`

## pseudocode

```c
__int64 __fastcall Enrollment::set_Discovery(Enrollment *this, HKEY a2, unsigned __int16 *a3)
{
  LSTATUS ValueW; // eax
  unsigned int v7; // ebx
  int v9; // ebx
  unsigned int v10; // ebx
  HANDLE ProcessHeap; // rax
  void *pvData; // rsi
  LSTATUS v13; // eax
  void *v14; // r14
  int v15; // edi
  HANDLE v16; // rax
  SIZE_T dwBytes; // [rsp+78h] [rbp+20h] BYREF

  LODWORD(dwBytes) = 0;
  ValueW = RegGetValueW(a2, a3, L"DiscoveryServiceFullURL", 2u, 0, 0, (LPDWORD)&dwBytes);
  v7 = ValueW;
  if ( ValueW == 2 )
    return 0;
  if ( ValueW )
  {
    if ( ValueW > 0 )
    {
      v9 = (unsigned __int16)ValueW;
      return v9 | 0x80070000;
    }
  }
  else
  {
    v10 = dwBytes;
    ProcessHeap = GetProcessHeap();
    pvData = HeapAlloc(ProcessHeap, 0, v10);
    if ( pvData )
    {
      v7 = 0;
      v13 = RegGetValueW(a2, a3, L"DiscoveryServiceFullURL", 2u, 0, pvData, (LPDWORD)&dwBytes);
      v14 = (void *)*((_QWORD *)this + 227);
      v15 = v13;
      *((_QWORD *)this + 227) = 0;
      if ( v14 )
      {
        v16 = GetProcessHeap();
        HeapFree(v16, 0, v14);
      }
      *((_QWORD *)this + 227) = pvData;
      if ( !v15 )
        return v7;
      if ( v15 > 0 )
      {
        v9 = (unsigned __int16)v15;
        return v9 | 0x80070000;
      }
      return (unsigned int)v15;
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18003f9b0  mov     r11, rsp
0x18003f9b3  mov     [r11+8], rbx
0x18003f9b7  mov     [r11+10h], rbp
0x18003f9bb  push    rsi
0x18003f9bc  push    rdi
0x18003f9bd  push    r14
0x18003f9bf  sub     rsp, 40h
0x18003f9c3  mov     rdi, r8
0x18003f9c6  mov     dword ptr [rsp+58h+dwBytes], 0
0x18003f9ce  mov     r14, rdx
0x18003f9d1  lea     rax, [r11+20h]
0x18003f9d5  mov     [r11-28h], rax
0x18003f9d9  lea     r8, aDiscoveryservi; "DiscoveryServiceFullURL"
0x18003f9e0  mov     rbp, rcx
0x18003f9e3  mov     qword ptr [r11-30h], 0
0x18003f9eb  mov     r9d, 2; dwFlags
0x18003f9f1  mov     qword ptr [r11-38h], 0
0x18003f9f9  mov     rdx, rdi; lpSubKey
0x18003f9fc  mov     rcx, r14; hkey
0x18003f9ff  call    cs:__imp_RegGetValueW
0x18003fa06  nop     dword ptr [rax+rax+00h]
0x18003fa0b  mov     ebx, eax
0x18003fa0d  cmp     eax, 2
0x18003fa10  jnz     short loc_18003FA19
0x18003fa12  xor     eax, eax
0x18003fa14  jmp     loc_18003FAE5
0x18003fa19  test    eax, eax
0x18003fa1b  jz      short loc_18003FA2B
0x18003fa1d  jle     loc_18003FAE3
0x18003fa23  movzx   ebx, ax
0x18003fa26  jmp     loc_18003FADD
0x18003fa2b  mov     ebx, dword ptr [rsp+58h+dwBytes]
0x18003fa2f  call    cs:__imp_GetProcessHeap
0x18003fa36  nop     dword ptr [rax+rax+00h]
0x18003fa3b  mov     r8d, ebx; dwBytes
0x18003fa3e  xor     edx, edx; dwFlags
0x18003fa40  mov     rcx, rax; hHeap
0x18003fa43  call    cs:__imp_HeapAlloc
0x18003fa4a  nop     dword ptr [rax+rax+00h]
0x18003fa4f  mov     rsi, rax
0x18003fa52  test    rax, rax
0x18003fa55  jnz     short loc_18003FA61
0x18003fa57  mov     ebx, 8007000Eh
0x18003fa5c  jmp     loc_18003FAE3
0x18003fa61  xor     ebx, ebx
0x18003fa63  lea     rax, [rsp+58h+dwBytes]
0x18003fa68  mov     [rsp+58h+pcbData], rax; pcbData
0x18003fa6d  lea     r8, aDiscoveryservi; "DiscoveryServiceFullURL"
0x18003fa74  mov     [rsp+58h+pvData], rsi; pvData
0x18003fa79  mov     rdx, rdi; lpSubKey
0x18003fa7c  mov     rcx, r14; hkey
0x18003fa7f  mov     [rsp+58h+pdwType], rbx; pdwType
0x18003fa84  lea     r9d, [rbx+2]; dwFlags
0x18003fa88  call    cs:__imp_RegGetValueW
0x18003fa8f  nop     dword ptr [rax+rax+00h]
0x18003fa94  mov     r14, [rbp+718h]
0x18003fa9b  mov     edi, eax
0x18003fa9d  mov     [rbp+718h], rbx
0x18003faa4  test    r14, r14
0x18003faa7  jz      short loc_18003FAC9
0x18003faa9  call    cs:__imp_GetProcessHeap
0x18003fab0  nop     dword ptr [rax+rax+00h]
0x18003fab5  mov     r8, r14; lpMem
0x18003fab8  xor     edx, edx; dwFlags
0x18003faba  mov     rcx, rax; hHeap
0x18003fabd  call    cs:__imp_HeapFree
0x18003fac4  nop     dword ptr [rax+rax+00h]
0x18003fac9  mov     [rbp+718h], rsi
0x18003fad0  test    edi, edi
0x18003fad2  jz      short loc_18003FAE3
0x18003fad4  jg      short loc_18003FADA
0x18003fad6  mov     ebx, edi
0x18003fad8  jmp     short loc_18003FAE3
0x18003fada  movzx   ebx, di
0x18003fadd  or      ebx, 80070000h
0x18003fae3  mov     eax, ebx
0x18003fae5  mov     rbx, [rsp+58h+arg_0]
0x18003faea  mov     rbp, [rsp+58h+arg_8]
0x18003faef  add     rsp, 40h
0x18003faf3  pop     r14
0x18003faf5  pop     rdi
0x18003faf6  pop     rsi
0x18003faf7  retn
```
