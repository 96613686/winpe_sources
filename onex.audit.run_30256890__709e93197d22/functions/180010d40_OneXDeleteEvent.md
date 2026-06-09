# OneXDeleteEvent

- ea: `0x180010d40`
- end: `0x180010f14`
- name: `OneXDeleteEvent`
- size: `468`
- prototype: ``
- caller_count: `24`
- callee_count: `6`
- tags: ``

## callers

- `0x180002020`
- `0x180003a1c`
- `0x180009540`
- `0x180009be0`
- `0x18000ade0`
- `0x18000ba30`
- `0x18000c870`
- `0x18000cd90`
- `0x18000d8d0`
- `0x18000dad0`
- `0x18000e6c0`
- `0x18000eab4`
- `0x18000ee70`
- `0x180010b20`
- `0x1800183c0`
- `0x180019080`
- `0x18001be88`
- `0x180023b6c`
- `0x180023f94`
- `0x1800240fc`
- `0x180024238`
- `0x1800243a4`
- `0x18002b6d0`
- `0x18002bbf8`

## callees

- `0x180005440`
- `0x180010ae0`
- `0x180010d40`
- `0x180019f7c`
- `0x1800214f0`
- `0x180022000`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010f09`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010f09`
- `MobileNetworking!FreeMemory` at `0x180010dd7`
- `MobileNetworking!FreeMemory` at `0x180010e32`
- `MobileNetworking!FreeMemory` at `0x180010eea`
- `MobileNetworking!FreeMemory` at `0x180010dd7`
- `MobileNetworking!FreeMemory` at `0x180010e32`
- `MobileNetworking!FreeMemory` at `0x180010eea`

## string_xrefs

- `0x180010dcb`: `OneXDeleteEvent`
- `0x180010e25`: `OneXDeleteEvent`
- `0x180010edd`: `OneXDeleteEvent`

## pseudocode

```c
__int64 __fastcall OneXDeleteEvent(__int64 a1)
{
  __int64 v1; // rdx
  _QWORD *v2; // rcx
  unsigned int v3; // edi
  __int64 i; // rbx
  __int64 v5; // r8
  void *v7; // rcx
  __int64 v8; // [rsp+30h] [rbp+8h] BYREF

  v8 = a1;
  v1 = a1;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 17, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids);
    v1 = v8;
    v2 = WPP_GLOBAL_Control;
  }
  if ( v1 )
  {
    v3 = 0;
    for ( i = 0; (unsigned int)i < *(_DWORD *)(v1 + 32); i = (unsigned int)(i + 1) )
    {
      v5 = 16LL * (unsigned int)i;
      switch ( *(_DWORD *)(v5 + v1 + 40) )
      {
        case 3:
          v7 = *(void **)(v1 + 16 * (i + 3));
          if ( !v7 )
            continue;
          CloseHandle(v7);
          break;
        case 5:
          FreeMemory(v5 + v1 + 48, "OneXDeleteEvent", 158);
          break;
        case 6:
          FreeMemory(v5 + v1 + 48, "OneXDeleteEvent", 162);
          break;
        case 7:
          if ( !*(_QWORD *)(v1 + 16 * (i + 3)) )
            continue;
          FreeEapAttributes();
          break;
        default:
          if ( *(_DWORD *)(v5 + v1 + 40) != 8 || !*(_QWORD *)(v1 + 16 * (i + 3)) )
            continue;
          OneXFreeRuntimeState();
          break;
      }
      v1 = v8;
    }
    FreeMemory(&v8, "OneXDeleteEvent", 190);
    goto LABEL_13;
  }
  v3 = 87;
  if ( v2 == &WPP_GLOBAL_Control )
    return v3;
  if ( (*((_BYTE *)v2 + 68) & 1) != 0 )
  {
    WPP_SF_d(v2[7], 18, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, 0);
LABEL_13:
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_DWORD *)v2 + 17) & 0x800) != 0 )
    WPP_SF_D(v2[7], 19, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x180010d40  mov     [rsp+arg_0], rcx
0x180010d45  push    rsi
0x180010d46  sub     rsp, 20h
0x180010d4a  mov     rdx, rcx
0x180010d4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180010d54  lea     rsi, WPP_GLOBAL_Control
0x180010d5b  cmp     rcx, rsi
0x180010d5e  jz      short loc_180010D6D
0x180010d60  test    dword ptr [rcx+44h], 800h
0x180010d67  jnz     loc_180010E5D
0x180010d6d  mov     [rsp+28h+arg_10], rdi
0x180010d72  test    rdx, rdx
0x180010d75  jz      loc_180010E83
0x180010d7b  mov     [rsp+28h+arg_8], rbx
0x180010d80  xor     edi, edi
0x180010d82  xor     ebx, ebx
0x180010d84  cmp     [rdx+20h], ebx
0x180010d87  jbe     short loc_180010DC5
0x180010d89  mov     r8d, ebx
0x180010d8c  shl     r8, 4
0x180010d90  mov     ecx, [r8+rdx+28h]
0x180010d95  sub     ecx, 3
0x180010d98  jz      loc_180010EF5
0x180010d9e  sub     ecx, 2
0x180010da1  jz      loc_180010ED6
0x180010da7  sub     ecx, 1
0x180010daa  jz      short loc_180010E1E
0x180010dac  sub     ecx, 1
0x180010daf  jz      loc_180010EB8
0x180010db5  cmp     ecx, 1
0x180010db8  jz      loc_180010E42
0x180010dbe  inc     ebx
0x180010dc0  cmp     ebx, [rdx+20h]
0x180010dc3  jb      short loc_180010D89
0x180010dc5  mov     r8d, 0BEh
0x180010dcb  lea     rdx, aOnexdeleteeven; "OneXDeleteEvent"
0x180010dd2  lea     rcx, [rsp+28h+arg_0]
0x180010dd7  call    cs:__imp_FreeMemory
0x180010ddd  mov     rbx, [rsp+28h+arg_8]
0x180010de2  mov     rcx, cs:WPP_GLOBAL_Control
0x180010de9  cmp     rcx, rsi
0x180010dec  jnz     short loc_180010DFB
0x180010dee  mov     eax, edi
0x180010df0  mov     rdi, [rsp+28h+arg_10]
0x180010df5  add     rsp, 20h
0x180010df9  pop     rsi
0x180010dfa  retn
0x180010dfb  test    dword ptr [rcx+44h], 800h
0x180010e02  jz      short loc_180010DEE
0x180010e04  mov     rcx, [rcx+38h]
0x180010e08  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x180010e0f  mov     edx, 13h
0x180010e14  mov     r9d, edi
0x180010e17  call    WPP_SF_D
0x180010e1c  jmp     short loc_180010DEE
0x180010e1e  lea     rcx, [rdx+30h]
0x180010e22  add     rcx, r8
0x180010e25  lea     rdx, aOnexdeleteeven; "OneXDeleteEvent"
0x180010e2c  mov     r8d, 0A2h
0x180010e32  call    cs:__imp_FreeMemory
0x180010e38  mov     rdx, [rsp+28h+arg_0]
0x180010e3d  jmp     loc_180010DBE
0x180010e42  lea     rax, [rbx+3]
0x180010e46  add     rax, rax
0x180010e49  mov     rcx, [rdx+rax*8]
0x180010e4d  test    rcx, rcx
0x180010e50  jz      loc_180010DBE
0x180010e56  call    OneXFreeRuntimeState
0x180010e5b  jmp     short loc_180010E38
0x180010e5d  mov     rcx, [rcx+38h]
0x180010e61  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x180010e68  mov     edx, 11h
0x180010e6d  call    WPP_SF_
0x180010e72  mov     rdx, [rsp+28h+arg_0]
0x180010e77  mov     rcx, cs:WPP_GLOBAL_Control
0x180010e7e  jmp     loc_180010D6D
0x180010e83  mov     edi, 57h ; 'W'
0x180010e88  cmp     rcx, rsi
0x180010e8b  jz      loc_180010DEE
0x180010e91  test    byte ptr [rcx+44h], 1
0x180010e95  jz      loc_180010DE9
0x180010e9b  mov     rcx, [rcx+38h]
0x180010e9f  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x180010ea6  mov     edx, 12h
0x180010eab  xor     r9d, r9d
0x180010eae  call    WPP_SF_d
0x180010eb3  jmp     loc_180010DE2
0x180010eb8  lea     rax, [rbx+3]
0x180010ebc  add     rax, rax
0x180010ebf  mov     rcx, [rdx+rax*8]
0x180010ec3  test    rcx, rcx
0x180010ec6  jz      loc_180010DBE
0x180010ecc  call    FreeEapAttributes
0x180010ed1  jmp     loc_180010E38
0x180010ed6  lea     rcx, [rdx+30h]
0x180010eda  add     rcx, r8
0x180010edd  lea     rdx, aOnexdeleteeven; "OneXDeleteEvent"
0x180010ee4  mov     r8d, 9Eh
0x180010eea  call    cs:__imp_FreeMemory
0x180010ef0  jmp     loc_180010E38
0x180010ef5  lea     rax, [rbx+3]
0x180010ef9  add     rax, rax
0x180010efc  mov     rcx, [rdx+rax*8]; hObject
0x180010f00  test    rcx, rcx
0x180010f03  jz      loc_180010DBE
0x180010f09  call    cs:__imp_CloseHandle
0x180010f0f  jmp     loc_180010E38
```
