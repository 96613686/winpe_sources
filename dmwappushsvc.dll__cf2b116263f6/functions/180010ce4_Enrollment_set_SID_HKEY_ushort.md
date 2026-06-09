# Enrollment::set_SID(HKEY__ *,ushort *)

- ea: `0x180010ce4`
- end: `0x180010de2`
- name: `?set_SID@Enrollment@@QEAAJPEAUHKEY__@@PEAG@Z`
- size: `254`
- prototype: `__int64 __fastcall(void **this, HKEY, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000df4c`

## callees

- `0x18000dcd8`
- `0x180010ce4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010d59`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010d59`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010d67`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010d67`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010d2f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010da6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010d2f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010da6`

## pseudocode

```c
__int64 __fastcall Enrollment::set_SID(void **this, HKEY a2, unsigned __int16 *a3)
{
  LSTATUS ValueW; // eax
  unsigned int v7; // edi
  int v9; // edi
  unsigned int v10; // ebx
  HANDLE ProcessHeap; // rax
  void *pvData; // rbp
  LSTATUS v13; // esi
  SIZE_T dwBytes; // [rsp+98h] [rbp+20h] BYREF

  LODWORD(dwBytes) = 0;
  ValueW = RegGetValueW(a2, a3, L"SID", 2u, 0, 0, (LPDWORD)&dwBytes);
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
      v13 = RegGetValueW(a2, a3, L"SID", 2u, 0, pvData, (LPDWORD)&dwBytes);
      CTSmartObj<unsigned short *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(this + 225);
      this[225] = pvData;
      if ( v13 )
      {
        if ( v13 > 0 )
        {
          v9 = (unsigned __int16)v13;
          return v9 | 0x80070000;
        }
        return (unsigned int)v13;
      }
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
0x180010ce4  mov     r11, rsp
0x180010ce7  push    rbx
0x180010ce8  push    rbp
0x180010ce9  push    rsi
0x180010cea  push    rdi
0x180010ceb  push    r14
0x180010ced  push    r15
0x180010cef  sub     rsp, 48h
0x180010cf3  mov     rsi, r8
0x180010cf6  mov     dword ptr [r11+20h], 0
0x180010cfe  mov     r14, rdx
0x180010d01  lea     rax, [r11+20h]
0x180010d05  mov     [r11-48h], rax
0x180010d09  lea     r8, aSid; "SID"
0x180010d10  mov     r15, rcx
0x180010d13  mov     qword ptr [r11-50h], 0
0x180010d1b  mov     r9d, 2; dwFlags
0x180010d21  mov     qword ptr [r11-58h], 0
0x180010d29  mov     rdx, rsi; lpSubKey
0x180010d2c  mov     rcx, r14; hkey
0x180010d2f  call    cs:__imp_RegGetValueW
0x180010d35  mov     edi, eax
0x180010d37  cmp     eax, 2
0x180010d3a  jnz     short loc_180010D43
0x180010d3c  xor     eax, eax
0x180010d3e  jmp     loc_180010DD5
0x180010d43  test    eax, eax
0x180010d45  jz      short loc_180010D52
0x180010d47  jle     loc_180010DD3
0x180010d4d  movzx   edi, ax
0x180010d50  jmp     short loc_180010DCD
0x180010d52  mov     ebx, dword ptr [rsp+78h+dwBytes]
0x180010d59  call    cs:__imp_GetProcessHeap
0x180010d5f  mov     r8d, ebx; dwBytes
0x180010d62  xor     edx, edx; dwFlags
0x180010d64  mov     rcx, rax; hHeap
0x180010d67  call    cs:__imp_HeapAlloc
0x180010d6d  mov     rbp, rax
0x180010d70  test    rax, rax
0x180010d73  jnz     short loc_180010D7C
0x180010d75  mov     edi, 8007000Eh
0x180010d7a  jmp     short loc_180010DD3
0x180010d7c  xor     edi, edi
0x180010d7e  lea     rax, [rsp+78h+dwBytes]
0x180010d86  mov     [rsp+78h+pcbData], rax; pcbData
0x180010d8b  lea     r8, aSid; "SID"
0x180010d92  mov     [rsp+78h+pvData], rbp; pvData
0x180010d97  mov     rdx, rsi; lpSubKey
0x180010d9a  mov     rcx, r14; hkey
0x180010d9d  mov     [rsp+78h+pdwType], rdi; pdwType
0x180010da2  lea     r9d, [rdi+2]; dwFlags
0x180010da6  call    cs:__imp_RegGetValueW
0x180010dac  lea     rbx, [r15+708h]
0x180010db3  mov     esi, eax
0x180010db5  mov     rcx, rbx
0x180010db8  call    ?Release@?$CTSmartObj@PEAGV?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyHeapMem@@@@@@QEAAXXZ; CTSmartObj<ushort *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(void)
0x180010dbd  mov     [rbx], rbp
0x180010dc0  test    esi, esi
0x180010dc2  jz      short loc_180010DD3
0x180010dc4  jg      short loc_180010DCA
0x180010dc6  mov     edi, esi
0x180010dc8  jmp     short loc_180010DD3
0x180010dca  movzx   edi, si
0x180010dcd  or      edi, 80070000h
0x180010dd3  mov     eax, edi
0x180010dd5  add     rsp, 48h
0x180010dd9  pop     r15
0x180010ddb  pop     r14
0x180010ddd  pop     rdi
0x180010dde  pop     rsi
0x180010ddf  pop     rbp
0x180010de0  pop     rbx
0x180010de1  retn
```
