# GetNameFromRegistry(HKEY__ *,ushort * *)

- ea: `0x180058894`
- end: `0x1800589e1`
- name: `?GetNameFromRegistry@@YAJPEAUHKEY__@@PEAPEAG@Z`
- size: `333`
- prototype: `__int64 __fastcall(HKEY hkey, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180056c20`
- `0x18005735c`

## callees

- `0x180058894`
- `0x1801200d0`
- `0x180121581`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800588f5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005894d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800588f5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005894d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800589d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800589d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180058915`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800589a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180058915`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800589a3`

## pseudocode

```c
__int64 __fastcall GetNameFromRegistry(HKEY hkey, LPVOID *a2)
{
  LSTATUS ValueW; // eax
  signed int v5; // ebx
  unsigned __int16 *pvData; // rax
  LSTATUS v7; // eax
  unsigned __int16 *v9; // rax
  DWORD pcbData[4]; // [rsp+40h] [rbp-A8h] BYREF
  _BYTE Src[128]; // [rsp+50h] [rbp-98h] BYREF

  *a2 = 0;
  pcbData[0] = 120;
  ValueW = RegGetValueW(hkey, 0, 0, 2u, 0, Src, pcbData);
  v5 = ValueW;
  if ( ValueW > 0 )
    v5 = (unsigned __int16)ValueW | 0x80070000;
  if ( v5 != -2147024662 )
  {
    if ( v5 < 0 )
      goto LABEL_13;
    v9 = (unsigned __int16 *)CoTaskMemAlloc(pcbData[0]);
    *a2 = v9;
    if ( v9 )
    {
      memcpy_0(v9, Src, pcbData[0]);
      return (unsigned int)v5;
    }
LABEL_12:
    v5 = -2147024882;
LABEL_13:
    if ( *a2 )
    {
      CoTaskMemFree(*a2);
      *a2 = 0;
    }
    return (unsigned int)v5;
  }
  pvData = (unsigned __int16 *)CoTaskMemAlloc(pcbData[0]);
  *a2 = pvData;
  if ( !pvData )
    goto LABEL_12;
  v7 = RegGetValueW(hkey, 0, 0, 2u, 0, pvData, pcbData);
  v5 = v7;
  if ( v7 > 0 )
    v5 = (unsigned __int16)v7 | 0x80070000;
  if ( v5 < 0 )
    goto LABEL_13;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180058894  mov     [rsp+arg_10], rbx
0x180058899  mov     [rsp+arg_18], rsi
0x18005889e  push    rdi
0x18005889f  sub     rsp, 0E0h
0x1800588a6  mov     rax, cs:__security_cookie
0x1800588ad  xor     rax, rsp
0x1800588b0  mov     [rsp+0E8h+var_18], rax
0x1800588b8  lea     rax, [rsp+0E8h+var_A8]
0x1800588bd  mov     qword ptr [rdx], 0
0x1800588c4  mov     [rsp+0E8h+pcbData], rax; pcbData
0x1800588c9  mov     rdi, rdx
0x1800588cc  lea     rax, [rsp+0E8h+Src]
0x1800588d1  mov     [rsp+0E8h+var_A8], 78h ; 'x'
0x1800588d9  mov     [rsp+0E8h+pvData], rax; pvData
0x1800588de  mov     r9d, 2; dwFlags
0x1800588e4  xor     r8d, r8d; lpValue
0x1800588e7  mov     [rsp+0E8h+pdwType], 0; pdwType
0x1800588f0  xor     edx, edx; lpSubKey
0x1800588f2  mov     rsi, rcx
0x1800588f5  call    cs:__imp_RegGetValueW
0x1800588fb  mov     ebx, eax
0x1800588fd  test    eax, eax
0x1800588ff  jg      loc_18005898D
0x180058905  cmp     ebx, 800700EAh
0x18005890b  jnz     loc_18005899B
0x180058911  mov     ecx, [rsp+0E8h+var_A8]; cb
0x180058915  call    cs:__imp_CoTaskMemAlloc
0x18005891b  mov     [rdi], rax
0x18005891e  test    rax, rax
0x180058921  jz      loc_1800589C5
0x180058927  lea     rcx, [rsp+0E8h+var_A8]
0x18005892c  mov     r9d, 2; dwFlags
0x180058932  mov     [rsp+0E8h+pcbData], rcx; pcbData
0x180058937  xor     r8d, r8d; lpValue
0x18005893a  mov     [rsp+0E8h+pvData], rax; pvData
0x18005893f  mov     rcx, rsi; hkey
0x180058942  xor     edx, edx; lpSubKey
0x180058944  mov     [rsp+0E8h+pdwType], 0; pdwType
0x18005894d  call    cs:__imp_RegGetValueW
0x180058953  mov     ebx, eax
0x180058955  test    eax, eax
0x180058957  jle     short loc_180058962
0x180058959  movzx   ebx, ax
0x18005895c  or      ebx, 80070000h
0x180058962  test    ebx, ebx
0x180058964  js      short loc_1800589CA
0x180058966  mov     eax, ebx
0x180058968  mov     rcx, [rsp+0E8h+var_18]
0x180058970  xor     rcx, rsp; StackCookie
0x180058973  call    __security_check_cookie
0x180058978  lea     r11, [rsp+0E8h+var_8]
0x180058980  mov     rbx, [r11+20h]
0x180058984  mov     rsi, [r11+28h]
0x180058988  mov     rsp, r11
0x18005898b  pop     rdi
0x18005898c  retn
0x18005898d  movzx   ebx, ax
0x180058990  or      ebx, 80070000h
0x180058996  jmp     loc_180058905
0x18005899b  test    ebx, ebx
0x18005899d  js      short loc_1800589CA
0x18005899f  mov     ecx, [rsp+0E8h+var_A8]; cb
0x1800589a3  call    cs:__imp_CoTaskMemAlloc
0x1800589a9  mov     [rdi], rax
0x1800589ac  test    rax, rax
0x1800589af  jz      short loc_1800589C5
0x1800589b1  mov     r8d, [rsp+0E8h+var_A8]; Size
0x1800589b6  lea     rdx, [rsp+0E8h+Src]; Src
0x1800589bb  mov     rcx, rax; void *
0x1800589be  call    memcpy_0
0x1800589c3  jmp     short loc_180058966
0x1800589c5  mov     ebx, 8007000Eh
0x1800589ca  mov     rcx, [rdi]; pv
0x1800589cd  test    rcx, rcx
0x1800589d0  jz      short loc_180058966
0x1800589d2  call    cs:__imp_CoTaskMemFree
0x1800589d8  mov     qword ptr [rdi], 0
0x1800589df  jmp     short loc_180058966
```
