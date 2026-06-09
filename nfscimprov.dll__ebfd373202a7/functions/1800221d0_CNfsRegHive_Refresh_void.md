# CNfsRegHive::Refresh(void)

- ea: `0x1800221d0`
- end: `0x180022312`
- name: `?Refresh@CNfsRegHive@@QEAAKXZ`
- size: `322`
- prototype: `unsigned int __fastcall(CNfsRegHive *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001209c`
- `0x18001248c`
- `0x180012690`
- `0x1800272a0`

## callees

- `0x1800221d0`
- `0x18002c874`

## import_xrefs

- `CLUSAPI!ClusterRegCreateKey` at `0x18002228c`
- `CLUSAPI!ClusterRegCreateKey` at `0x18002228c`
- `CLUSAPI!ClusterRegQueryValue` at `0x1800222ba`
- `CLUSAPI!ClusterRegQueryValue` at `0x1800222ba`
- `CLUSAPI!ClusterRegSetValue` at `0x180022301`
- `CLUSAPI!ClusterRegSetValue` at `0x180022301`
- `CLUSAPI!ClusterRegDeleteValue` at `0x1800222e7`
- `CLUSAPI!ClusterRegDeleteValue` at `0x1800222e7`

## string_xrefs

- `0x180022278`: `ServerForNFS\ReadConfig`

## pseudocode

```c
LONG __fastcall CNfsRegHive::Refresh(CNfsRegHive *this)
{
  LONG result; // eax
  HKEY *v2; // rbx
  HKEY v3; // rcx
  int v4; // eax
  int Data; // [rsp+70h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+38h] BYREF
  DWORD dwValueType; // [rsp+80h] [rbp+40h] BYREF
  DWORD dwDisposition; // [rsp+88h] [rbp+48h] BYREF

  cbData = 0;
  Data = 0;
  dwValueType = 0;
  dwDisposition = 0;
  if ( *((_DWORD *)this + 1) )
    return 5;
  if ( *(_DWORD *)this )
  {
    v2 = (HKEY *)((char *)this + 40);
    result = ClusterRegCreateKey(
               *((HKEY *)this + 2),
               L"ServerForNFS\\ReadConfig",
               0,
               0x2001Fu,
               0,
               (PHKEY)this + 5,
               &dwDisposition);
    if ( result )
      return result;
    v3 = *v2;
    cbData = 4;
    result = ClusterRegQueryValue(v3, L"Default", &dwValueType, (LPBYTE)&Data, &cbData);
    if ( result != 2 )
    {
      if ( result )
        return result;
      if ( dwValueType == 4 )
      {
        if ( Data == -1 )
          v4 = 0;
        else
          v4 = Data + 1;
        Data = v4;
        return ClusterRegSetValue(*v2, L"Default", 4u, (const BYTE *)&Data, 4u);
      }
      ClusterRegDeleteValue(*v2, L"Default");
    }
    Data = 0;
    return ClusterRegSetValue(*v2, L"Default", 4u, (const BYTE *)&Data, 4u);
  }
  result = NfsDeviceIoControl(L"\\\\.\\NfsSvr", 0xC0000000, 0x10008440u, 0, 0, 0, 0, 0);
  if ( !result )
    return NfsDeviceIoControl(L"\\\\.\\NfsSvr", 0xC0000000, 0x10008490u, 0, 0, 0, 0, 0);
  return result;
}

```

## disassembly

```asm
0x1800221d0  push    rbp
0x1800221d2  push    rbx
0x1800221d3  push    rsi
0x1800221d4  push    rdi
0x1800221d5  push    r14
0x1800221d7  mov     rbp, rsp
0x1800221da  sub     rsp, 40h
0x1800221de  xor     edi, edi
0x1800221e0  mov     [rbp+cbData], edi
0x1800221e3  mov     [rbp+Data], edi
0x1800221e6  mov     [rbp+dwValueType], edi
0x1800221e9  mov     [rbp+dwDisposition], edi
0x1800221ec  cmp     [rcx+4], edi
0x1800221ef  jz      short loc_1800221F9
0x1800221f1  lea     eax, [rdi+5]
0x1800221f4  jmp     loc_180022307
0x1800221f9  cmp     [rcx], edi
0x1800221fb  jnz     short loc_180022261
0x1800221fd  mov     [rsp+40h+var_8], rdi; unsigned int *
0x180022202  lea     rcx, aNfssvr; "\\\\.\\NfsSvr"
0x180022209  mov     dword ptr [rsp+40h+lpdwDisposition], edi; unsigned int
0x18002220d  mov     ebx, 0C0000000h
0x180022212  mov     [rsp+40h+phkResult], rdi; void *
0x180022217  mov     edx, ebx; unsigned int
0x180022219  xor     r9d, r9d; void *
0x18002221c  mov     dword ptr [rsp+40h+lpSecurityAttributes], edi; unsigned int
0x180022220  mov     r8d, 10008440h; unsigned int
0x180022226  call    ?NfsDeviceIoControl@@YAKPEBGKKPEAXK1KPEAK@Z; NfsDeviceIoControl(ushort const *,ulong,ulong,void *,ulong,void *,ulong,ulong *)
0x18002222b  test    eax, eax
0x18002222d  jnz     loc_180022307
0x180022233  mov     [rsp+40h+var_8], rdi; unsigned int *
0x180022238  lea     rcx, aNfssvr; "\\\\.\\NfsSvr"
0x18002223f  mov     dword ptr [rsp+40h+lpdwDisposition], edi; unsigned int
0x180022243  xor     r9d, r9d; void *
0x180022246  mov     [rsp+40h+phkResult], rdi; void *
0x18002224b  mov     r8d, 10008490h; unsigned int
0x180022251  mov     edx, ebx; unsigned int
0x180022253  mov     dword ptr [rsp+40h+lpSecurityAttributes], edi; unsigned int
0x180022257  call    ?NfsDeviceIoControl@@YAKPEBGKKPEAXK1KPEAK@Z; NfsDeviceIoControl(ushort const *,ulong,ulong,void *,ulong,void *,ulong,ulong *)
0x18002225c  jmp     loc_180022307
0x180022261  lea     rbx, [rcx+28h]
0x180022265  mov     r9d, 2001Fh; samDesired
0x18002226b  mov     rcx, [rcx+10h]; hKey
0x18002226f  lea     rax, [rbp+dwDisposition]
0x180022273  mov     [rsp+40h+lpdwDisposition], rax; lpdwDisposition
0x180022278  lea     rdx, aServerfornfsRe; "ServerForNFS\\ReadConfig"
0x18002227f  mov     [rsp+40h+phkResult], rbx; phkResult
0x180022284  xor     r8d, r8d; dwOptions
0x180022287  mov     [rsp+40h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18002228c  call    cs:__imp_ClusterRegCreateKey
0x180022292  test    eax, eax
0x180022294  jnz     short loc_180022307
0x180022296  mov     rcx, [rbx]; hKey
0x180022299  lea     esi, [rax+4]
0x18002229c  lea     rax, [rbp+cbData]
0x1800222a0  mov     [rbp+cbData], esi
0x1800222a3  lea     r14, szValueName; "Default"
0x1800222aa  mov     [rsp+40h+lpSecurityAttributes], rax; lpcbData
0x1800222af  mov     rdx, r14; lpszValueName
0x1800222b2  lea     r9, [rbp+Data]; lpData
0x1800222b6  lea     r8, [rbp+dwValueType]; lpdwValueType
0x1800222ba  call    cs:__imp_ClusterRegQueryValue
0x1800222c0  cmp     eax, 2
0x1800222c3  jz      short loc_1800222ED
0x1800222c5  test    eax, eax
0x1800222c7  jnz     short loc_180022307
0x1800222c9  cmp     [rbp+dwValueType], esi
0x1800222cc  jnz     short loc_1800222E1
0x1800222ce  mov     eax, [rbp+Data]
0x1800222d1  cmp     eax, 0FFFFFFFFh
0x1800222d4  jnz     short loc_1800222DA
0x1800222d6  mov     eax, edi
0x1800222d8  jmp     short loc_1800222DC
0x1800222da  inc     eax
0x1800222dc  mov     [rbp+Data], eax
0x1800222df  jmp     short loc_1800222F0
0x1800222e1  mov     rcx, [rbx]; hKey
0x1800222e4  mov     rdx, r14; lpszValueName
0x1800222e7  call    cs:__imp_ClusterRegDeleteValue
0x1800222ed  mov     [rbp+Data], edi
0x1800222f0  mov     rcx, [rbx]; hKey
0x1800222f3  lea     r9, [rbp+Data]; lpData
0x1800222f7  mov     r8d, esi; dwType
0x1800222fa  mov     dword ptr [rsp+40h+lpSecurityAttributes], esi; cbData
0x1800222fe  mov     rdx, r14; lpszValueName
0x180022301  call    cs:__imp_ClusterRegSetValue
0x180022307  add     rsp, 40h
0x18002230b  pop     r14
0x18002230d  pop     rdi
0x18002230e  pop     rsi
0x18002230f  pop     rbx
0x180022310  pop     rbp
0x180022311  retn
```
