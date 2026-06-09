# CPnpDiskCleanupHandler::InitializeEx(HKEY__ *,ushort const *,ushort const *,ushort * *,ushort * *,ushort * *,ulong *)

- ea: `0x180003140`
- end: `0x180003278`
- name: `?InitializeEx@CPnpDiskCleanupHandler@@UEAAJPEAUHKEY__@@PEBG1PEAPEAG22PEAK@Z`
- size: `312`
- prototype: `__int64 __fastcall(CPnpDiskCleanupHandler *this, HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **Src, unsigned __int16 **, unsigned __int16 **, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180003140`
- `0x1800041cc`
- `0x180008e30`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x1800031ed`
- `KERNEL32!CompareStringOrdinal` at `0x1800031ed`
- `KERNEL32!GetSystemDirectoryW` at `0x1800031ad`
- `KERNEL32!GetSystemDirectoryW` at `0x1800031ad`
- `ole32!CoTaskMemFree` at `0x18000323e`
- `ole32!CoTaskMemFree` at `0x18000323e`
- `SETUPAPI!pSetupIsUserAdmin` at `0x180003195`
- `SETUPAPI!pSetupIsUserAdmin` at `0x180003195`

## pseudocode

```c
__int64 __fastcall CPnpDiskCleanupHandler::InitializeEx(
        CPnpDiskCleanupHandler *this,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 **Src,
        unsigned __int16 **a6,
        unsigned __int16 **a7,
        unsigned int *a8)
{
  unsigned __int64 v10; // rax
  __int64 v11; // r8
  void *v12; // r9
  int v13; // edi
  __int64 v14; // r8
  void *v15; // r9
  BOOL bIgnoreCase; // [rsp+20h] [rbp-248h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-248h]
  WCHAR Buffer[264]; // [rsp+30h] [rbp-238h] BYREF

  *Src = 0;
  *a6 = 0;
  *a7 = 0;
  if ( !(unsigned int)pSetupIsUserAdmin(this) )
    return 1;
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
    return 2147500037LL;
  v10 = -1;
  do
    ++v10;
  while ( a3[v10] );
  if ( v10 < 3 || CompareStringOrdinal(Buffer, 3, a3, 3, 1) != 2 || (*(_BYTE *)a8 & 0x20) != 0 )
    return 1;
  v13 = TResourceStringAllocCopyEx<unsigned short *>(*(HMODULE *)&g_hModule, 101, v11, v12, bIgnoreCase, (void **)Src);
  if ( v13 >= 0 )
  {
    v13 = TResourceStringAllocCopyEx<unsigned short *>(*(HMODULE *)&g_hModule, 102, v14, v15, bIgnoreCasea, (void **)a6);
    if ( v13 < 0 )
    {
      CoTaskMemFree(*Src);
      *Src = 0;
    }
    else
    {
      *a8 &= ~0x10u;
      *a8 |= 2u;
    }
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180003140  mov     [rsp+arg_0], rbx
0x180003145  mov     [rsp+arg_8], rbp
0x18000314a  push    rsi
0x18000314b  push    rdi
0x18000314c  push    r14
0x18000314e  sub     rsp, 250h
0x180003155  mov     rax, cs:__security_cookie
0x18000315c  xor     rax, rsp
0x18000315f  mov     [rsp+268h+var_28], rax
0x180003167  mov     rax, [rsp+268h+arg_30]
0x18000316f  xor     ebp, ebp
0x180003171  mov     rsi, [rsp+268h+arg_20]
0x180003179  mov     rdi, r8
0x18000317c  mov     r14, [rsp+268h+arg_28]
0x180003184  mov     rbx, [rsp+268h+arg_38]
0x18000318c  mov     [rsi], rbp
0x18000318f  mov     [r14], rbp
0x180003192  mov     [rax], rbp
0x180003195  call    cs:__imp_pSetupIsUserAdmin
0x18000319b  test    eax, eax
0x18000319d  jz      loc_18000324B
0x1800031a3  mov     edx, 104h; uSize
0x1800031a8  lea     rcx, [rsp+268h+Buffer]; lpBuffer
0x1800031ad  call    cs:__imp_GetSystemDirectoryW
0x1800031b3  test    eax, eax
0x1800031b5  jnz     short loc_1800031C1
0x1800031b7  mov     eax, 80004005h
0x1800031bc  jmp     loc_180003250
0x1800031c1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800031c5  inc     rax
0x1800031c8  cmp     [rdi+rax*2], bp
0x1800031cc  jnz     short loc_1800031C5
0x1800031ce  cmp     rax, 3
0x1800031d2  jb      short loc_18000324B
0x1800031d4  mov     r9d, 3; cchCount2
0x1800031da  mov     [rsp+268h+bIgnoreCase], 1; int
0x1800031e2  mov     edx, r9d; cchCount1
0x1800031e5  lea     rcx, [rsp+268h+Buffer]; lpString1
0x1800031ea  mov     r8, rdi; lpString2
0x1800031ed  call    cs:__imp_CompareStringOrdinal
0x1800031f3  cmp     eax, 2
0x1800031f6  jnz     short loc_18000324B
0x1800031f8  test    byte ptr [rbx], 20h
0x1800031fb  jnz     short loc_18000324B
0x1800031fd  mov     rcx, cs:?g_hModule@@3PEAUHINSTANCE__@@EA; int
0x180003204  lea     edx, [rax+63h]; int
0x180003207  mov     [rsp+268h+Src], rsi; Src
0x18000320c  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x180003211  mov     edi, eax
0x180003213  test    eax, eax
0x180003215  js      short loc_180003247
0x180003217  mov     rcx, cs:?g_hModule@@3PEAUHINSTANCE__@@EA; int
0x18000321e  mov     edx, 66h ; 'f'; int
0x180003223  mov     [rsp+268h+Src], r14; Src
0x180003228  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x18000322d  mov     edi, eax
0x18000322f  test    eax, eax
0x180003231  js      short loc_18000323B
0x180003233  and     dword ptr [rbx], 0FFFFFFEFh
0x180003236  or      dword ptr [rbx], 2
0x180003239  jmp     short loc_180003247
0x18000323b  mov     rcx, [rsi]; pv
0x18000323e  call    cs:__imp_CoTaskMemFree
0x180003244  mov     [rsi], rbp
0x180003247  mov     eax, edi
0x180003249  jmp     short loc_180003250
0x18000324b  mov     eax, 1
0x180003250  mov     rcx, [rsp+268h+var_28]
0x180003258  xor     rcx, rsp; StackCookie
0x18000325b  call    __security_check_cookie
0x180003260  lea     r11, [rsp+268h+var_18]
0x180003268  mov     rbx, [r11+20h]
0x18000326c  mov     rbp, [r11+28h]
0x180003270  mov     rsp, r11
0x180003273  pop     r14
0x180003275  pop     rdi
0x180003276  pop     rsi
0x180003277  retn
```
