# CscPolicy_ReadCacheQuotaPolicyValue(HKEY__ *,ushort const *,unsigned __int64,unsigned __int64 *)

- ea: `0x180013584`
- end: `0x18001370b`
- name: `?CscPolicy_ReadCacheQuotaPolicyValue@@YAJPEAUHKEY__@@PEBG_KPEA_K@Z`
- size: `391`
- prototype: `int(HKEY, const unsigned __int16 *, unsigned __int64, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180013138`

## callees

- `0x180008810`
- `0x180013584`
- `0x180014068`
- `0x1800140c8`
- `0x180014418`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800135ce`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800135ce`

## pseudocode

```c
__int64 __fastcall CscPolicy_ReadCacheQuotaPolicyValue(
        HKEY a1,
        const unsigned __int16 *a2,
        unsigned __int64 a3,
        unsigned __int64 *a4)
{
  LSTATUS v7; // eax
  signed int v8; // ebx
  unsigned __int64 v10[7]; // [rsp+30h] [rbp-38h] BYREF
  DWORD v11; // [rsp+88h] [rbp+20h] BYREF

  *a4 = 0;
  v10[0] = 0x400000000LL;
  v11 = 0;
  v7 = RegQueryValueExW(a1, a2, 0, &v11, (LPBYTE)v10, (LPDWORD)v10 + 1);
  v8 = v7;
  if ( v7 )
  {
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
    if ( (_WORD)v8 == 2 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(char *)(WPP_GLOBAL_Control + 28LL) < 0 )
        WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 22, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids, a2);
      *a4 = a3;
      return 0;
    }
    else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(char *)(WPP_GLOBAL_Control + 28LL) < 0 )
    {
      WPP_SF_SD(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        23,
        (unsigned int)WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids,
        (_DWORD)a2,
        v8);
    }
  }
  else if ( v11 == 4 )
  {
    v8 = ULongLongMult(LODWORD(v10[0]), 0x100000u, a4);
    if ( v8 < 0
      && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
    {
      WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 25, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids, a2);
    }
  }
  else
  {
    v8 = -2147024883;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_Sdd(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 24, v11, (_DWORD)a2, 4, v11);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180013584  mov     r11, rsp
0x180013587  push    rbx
0x180013588  push    rbp
0x180013589  push    rsi
0x18001358a  push    rdi
0x18001358b  sub     rsp, 48h
0x18001358f  lea     rax, [r11-34h]
0x180013593  mov     qword ptr [r9], 0
0x18001359a  mov     [r11-40h], rax
0x18001359e  mov     rsi, r9
0x1800135a1  lea     rax, [r11-38h]
0x1800135a5  mov     dword ptr [rsp+68h+var_38], 0
0x1800135ad  mov     rbp, r8
0x1800135b0  mov     [r11-48h], rax
0x1800135b4  lea     r9, [r11+20h]; lpType
0x1800135b8  mov     dword ptr [r11+20h], 0
0x1800135c0  xor     r8d, r8d; lpReserved
0x1800135c3  mov     dword ptr [rsp+68h+var_38+4], 4
0x1800135cb  mov     rdi, rdx
0x1800135ce  call    cs:__imp_RegQueryValueExW
0x1800135d4  mov     ebx, eax
0x1800135d6  test    eax, eax
0x1800135d8  jz      loc_18001366C
0x1800135de  jle     short loc_1800135E9
0x1800135e0  movzx   ebx, ax
0x1800135e3  or      ebx, 80070000h
0x1800135e9  cmp     bx, 2
0x1800135ed  jnz     short loc_18001362A
0x1800135ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800135f6  lea     rax, WPP_GLOBAL_Control
0x1800135fd  cmp     rcx, rax
0x180013600  jz      short loc_180013620
0x180013602  test    byte ptr [rcx+1Ch], 80h
0x180013606  jz      short loc_180013620
0x180013608  mov     rcx, [rcx+10h]
0x18001360c  lea     r8, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids
0x180013613  mov     edx, 16h
0x180013618  mov     r9, rdi
0x18001361b  call    WPP_SF_S
0x180013620  mov     [rsi], rbp
0x180013623  xor     ebx, ebx
0x180013625  jmp     loc_180013700
0x18001362a  mov     rcx, cs:WPP_GLOBAL_Control
0x180013631  lea     rax, WPP_GLOBAL_Control
0x180013638  cmp     rcx, rax
0x18001363b  jz      loc_180013700
0x180013641  test    byte ptr [rcx+1Ch], 80h
0x180013645  jz      loc_180013700
0x18001364b  mov     rcx, [rcx+10h]
0x18001364f  lea     r8, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids
0x180013656  mov     edx, 17h
0x18001365b  mov     [rsp+68h+var_48], ebx
0x18001365f  mov     r9, rdi
0x180013662  call    WPP_SF_SD
0x180013667  jmp     loc_180013700
0x18001366c  mov     r8d, [rsp+68h+arg_18]
0x180013674  cmp     r8d, 4
0x180013678  jz      short loc_1800136B8
0x18001367a  mov     ebx, 8007000Dh
0x18001367f  mov     rcx, cs:WPP_GLOBAL_Control
0x180013686  lea     rax, WPP_GLOBAL_Control
0x18001368d  cmp     rcx, rax
0x180013690  jz      short loc_180013700
0x180013692  test    byte ptr [rcx+1Ch], 2
0x180013696  jz      short loc_180013700
0x180013698  mov     rcx, [rcx+10h]
0x18001369c  mov     edx, 18h
0x1800136a1  mov     [rsp+68h+var_40], r8d
0x1800136a6  mov     r9, rdi
0x1800136a9  mov     [rsp+68h+var_48], 4
0x1800136b1  call    WPP_SF_Sdd
0x1800136b6  jmp     short loc_180013700
0x1800136b8  mov     ecx, dword ptr [rsp+68h+var_38]; unsigned __int64
0x1800136bc  mov     r8, rsi; unsigned __int64 *
0x1800136bf  mov     edx, 100000h; unsigned __int64
0x1800136c4  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800136c9  mov     ebx, eax
0x1800136cb  test    eax, eax
0x1800136cd  jns     short loc_180013700
0x1800136cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800136d6  lea     rax, WPP_GLOBAL_Control
0x1800136dd  cmp     rcx, rax
0x1800136e0  jz      short loc_180013700
0x1800136e2  test    byte ptr [rcx+1Ch], 2
0x1800136e6  jz      short loc_180013700
0x1800136e8  mov     rcx, [rcx+10h]
0x1800136ec  lea     r8, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids
0x1800136f3  mov     edx, 19h
0x1800136f8  mov     r9, rdi
0x1800136fb  call    WPP_SF_S
0x180013700  mov     eax, ebx
0x180013702  add     rsp, 48h
0x180013706  pop     rdi
0x180013707  pop     rsi
0x180013708  pop     rbp
0x180013709  pop     rbx
0x18001370a  retn
```
