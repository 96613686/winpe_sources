# Enrollment::set_Discovery(HKEY__ *,ushort *)

- ea: `0x1800109f8`
- end: `0x180010af6`
- name: `?set_Discovery@Enrollment@@QEAAJPEAUHKEY__@@PEAG@Z`
- size: `254`
- prototype: `__int64 __fastcall(void **this, HKEY, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000df4c`

## callees

- `0x18000dcd8`
- `0x1800109f8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010a6d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010a6d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010a7b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010a7b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010a43`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010aba`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010a43`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010aba`

## string_xrefs

- `0x180010a1d`: `DiscoveryServiceFullURL`
- `0x180010a9f`: `DiscoveryServiceFullURL`

## pseudocode

```c
__int64 __fastcall Enrollment::set_Discovery(void **this, HKEY a2, unsigned __int16 *a3)
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
      CTSmartObj<unsigned short *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(this + 227);
      this[227] = pvData;
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
0x1800109f8  mov     r11, rsp
0x1800109fb  push    rbx
0x1800109fc  push    rbp
0x1800109fd  push    rsi
0x1800109fe  push    rdi
0x1800109ff  push    r14
0x180010a01  push    r15
0x180010a03  sub     rsp, 48h
0x180010a07  mov     rsi, r8
0x180010a0a  mov     dword ptr [r11+20h], 0
0x180010a12  mov     r14, rdx
0x180010a15  lea     rax, [r11+20h]
0x180010a19  mov     [r11-48h], rax
0x180010a1d  lea     r8, aDiscoveryservi; "DiscoveryServiceFullURL"
0x180010a24  mov     r15, rcx
0x180010a27  mov     qword ptr [r11-50h], 0
0x180010a2f  mov     r9d, 2; dwFlags
0x180010a35  mov     qword ptr [r11-58h], 0
0x180010a3d  mov     rdx, rsi; lpSubKey
0x180010a40  mov     rcx, r14; hkey
0x180010a43  call    cs:__imp_RegGetValueW
0x180010a49  mov     edi, eax
0x180010a4b  cmp     eax, 2
0x180010a4e  jnz     short loc_180010A57
0x180010a50  xor     eax, eax
0x180010a52  jmp     loc_180010AE9
0x180010a57  test    eax, eax
0x180010a59  jz      short loc_180010A66
0x180010a5b  jle     loc_180010AE7
0x180010a61  movzx   edi, ax
0x180010a64  jmp     short loc_180010AE1
0x180010a66  mov     ebx, dword ptr [rsp+78h+dwBytes]
0x180010a6d  call    cs:__imp_GetProcessHeap
0x180010a73  mov     r8d, ebx; dwBytes
0x180010a76  xor     edx, edx; dwFlags
0x180010a78  mov     rcx, rax; hHeap
0x180010a7b  call    cs:__imp_HeapAlloc
0x180010a81  mov     rbp, rax
0x180010a84  test    rax, rax
0x180010a87  jnz     short loc_180010A90
0x180010a89  mov     edi, 8007000Eh
0x180010a8e  jmp     short loc_180010AE7
0x180010a90  xor     edi, edi
0x180010a92  lea     rax, [rsp+78h+dwBytes]
0x180010a9a  mov     [rsp+78h+pcbData], rax; pcbData
0x180010a9f  lea     r8, aDiscoveryservi; "DiscoveryServiceFullURL"
0x180010aa6  mov     [rsp+78h+pvData], rbp; pvData
0x180010aab  mov     rdx, rsi; lpSubKey
0x180010aae  mov     rcx, r14; hkey
0x180010ab1  mov     [rsp+78h+pdwType], rdi; pdwType
0x180010ab6  lea     r9d, [rdi+2]; dwFlags
0x180010aba  call    cs:__imp_RegGetValueW
0x180010ac0  lea     rbx, [r15+718h]
0x180010ac7  mov     esi, eax
0x180010ac9  mov     rcx, rbx
0x180010acc  call    ?Release@?$CTSmartObj@PEAGV?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyHeapMem@@@@@@QEAAXXZ; CTSmartObj<ushort *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(void)
0x180010ad1  mov     [rbx], rbp
0x180010ad4  test    esi, esi
0x180010ad6  jz      short loc_180010AE7
0x180010ad8  jg      short loc_180010ADE
0x180010ada  mov     edi, esi
0x180010adc  jmp     short loc_180010AE7
0x180010ade  movzx   edi, si
0x180010ae1  or      edi, 80070000h
0x180010ae7  mov     eax, edi
0x180010ae9  add     rsp, 48h
0x180010aed  pop     r15
0x180010aef  pop     r14
0x180010af1  pop     rdi
0x180010af2  pop     rsi
0x180010af3  pop     rbp
0x180010af4  pop     rbx
0x180010af5  retn
```
