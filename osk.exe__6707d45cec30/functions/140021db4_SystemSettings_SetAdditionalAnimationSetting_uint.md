# SystemSettings::SetAdditionalAnimationSetting(uint)

- ea: `0x140021db4`
- end: `0x140021e56`
- name: `?SetAdditionalAnimationSetting@SystemSettings@@CAJI@Z`
- size: `162`
- prototype: `__int64 __fastcall(PVOID pvParam)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140021f84`

## callees

- `0x140021db4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140021e10`
- `KERNEL32!GetLastError` at `0x140021e10`
- `USER32!SystemParametersInfoW` at `0x140021e02`
- `USER32!SystemParametersInfoW` at `0x140021e3a`
- `USER32!SystemParametersInfoW` at `0x140021e02`
- `USER32!SystemParametersInfoW` at `0x140021e3a`

## pseudocode

```c
signed int __fastcall SystemSettings::SetAdditionalAnimationSetting(PVOID pvParam)
{
  unsigned __int64 v1; // rdi
  unsigned int v2; // ebx
  signed int result; // eax
  UINT uiAction[10]; // [rsp+20h] [rbp-28h]
  int pvParama; // [rsp+58h] [rbp+10h] BYREF
  int v6; // [rsp+5Ch] [rbp+14h]

  v1 = (unsigned int)pvParam;
  v2 = 0;
  uiAction[0] = 4099;
  uiAction[1] = 4101;
  uiAction[2] = 4103;
  uiAction[3] = 4117;
  uiAction[4] = 4119;
  while ( v2 < 5 )
  {
    if ( !SystemParametersInfoW(uiAction[v2], 0, (PVOID)v1, 3u) )
      goto LABEL_5;
    ++v2;
  }
  pvParama = 8;
  v6 = v1;
  if ( SystemParametersInfoW(0x49u, 0, &pvParama, 3u) )
    return 0;
LABEL_5:
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140021db4  mov     rax, rsp
0x140021db7  mov     [rax+8], rbx
0x140021dbb  mov     [rax+18h], rsi
0x140021dbf  push    rdi
0x140021dc0  sub     rsp, 40h
0x140021dc4  mov     edi, ecx
0x140021dc6  xor     ebx, ebx
0x140021dc8  mov     dword ptr [rax-28h], 1003h
0x140021dcf  mov     dword ptr [rax-24h], 1005h
0x140021dd6  mov     dword ptr [rax-20h], 1007h
0x140021ddd  mov     dword ptr [rax-1Ch], 1015h
0x140021de4  mov     dword ptr [rax-18h], 1017h
0x140021deb  xor     edx, edx; uiParam
0x140021ded  mov     r9d, 3; fWinIni
0x140021df3  cmp     ebx, 5
0x140021df6  jnb     short loc_140021E24
0x140021df8  movsxd  rcx, ebx
0x140021dfb  mov     r8, rdi; pvParam
0x140021dfe  mov     ecx, [rsp+rcx*4+48h+uiAction]; uiAction
0x140021e02  call    cs:__imp_SystemParametersInfoW
0x140021e08  test    eax, eax
0x140021e0a  jz      short loc_140021E10
0x140021e0c  inc     ebx
0x140021e0e  jmp     short loc_140021DEB
0x140021e10  call    cs:__imp_GetLastError
0x140021e16  test    eax, eax
0x140021e18  jle     short loc_140021E46
0x140021e1a  movzx   eax, ax
0x140021e1d  or      eax, 80070000h
0x140021e22  jmp     short loc_140021E46
0x140021e24  lea     r8, [rsp+48h+pvParam]; pvParam
0x140021e29  mov     [rsp+48h+pvParam], 8
0x140021e31  mov     ecx, 49h ; 'I'; uiAction
0x140021e36  mov     [rsp+48h+arg_C], edi
0x140021e3a  call    cs:__imp_SystemParametersInfoW
0x140021e40  test    eax, eax
0x140021e42  jz      short loc_140021E10
0x140021e44  xor     eax, eax
0x140021e46  mov     rbx, [rsp+48h+arg_0]
0x140021e4b  mov     rsi, [rsp+48h+arg_10]
0x140021e50  add     rsp, 40h
0x140021e54  pop     rdi
0x140021e55  retn
```
