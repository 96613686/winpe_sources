# DeleteFont(HFONT__ *)

- ea: `0x180071d50`
- end: `0x180071e50`
- name: `?DeleteFont@@YAHPEAUHFONT__@@@Z`
- size: `256`
- prototype: `__int64 __fastcall(HFONT)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180036218`
- `0x1800710c4`
- `0x180071d50`

## import_xrefs

- `GDI32!GdiGetEntry` at `0x180071da0`
- `GDI32!GdiGetEntry` at `0x180071e18`
- `GDI32!GdiGetEntry` at `0x180071da0`
- `GDI32!GdiGetEntry` at `0x180071e18`
- `GDI32!gW32PID` at `0x180071dc9`
- `GDI32!gCookie` at `0x180071de3`
- `GDI32!gMaxGdiHandleCount` at `0x180071d82`
- `ntdll!RtlEnterCriticalSection` at `0x180071d74`
- `ntdll!RtlEnterCriticalSection` at `0x180071d74`
- `ntdll!RtlLeaveCriticalSection` at `0x180071e3d`
- `ntdll!RtlLeaveCriticalSection` at `0x180071e3d`
- `win32u!NtGdiDeleteObjectApp` at `0x180071e2e`
- `win32u!NtGdiDeleteObjectApp` at `0x180071e2e`

## pseudocode

```c
__int64 __fastcall DeleteFont(unsigned __int64 a1)
{
  unsigned int v2; // eax
  __int64 v3; // rdx
  unsigned int v4; // eax
  unsigned __int64 v5; // rcx
  unsigned int v6; // ebx
  __int128 v8; // [rsp+20h] [rbp-30h] BYREF
  __int64 v9; // [rsp+30h] [rbp-20h]
  __int128 v10; // [rsp+38h] [rbp-18h] BYREF
  __int64 v11; // [rsp+48h] [rbp-8h]

  v10 = 0;
  v11 = 0;
  RtlEnterCriticalSection(&semLocal);
  v2 = HANDLE_TO_INDEX(a1);
  if ( v2 < gMaxGdiHandleCount )
  {
    v9 = 0;
    v8 = 0;
    if ( (int)GdiGetEntry(v2, &v8) >= 0
      && BYTE14(v8) == 10
      && WORD6(v8) == WORD1(a1)
      && (DWORD2(v8) & 0xFFFFFFFE) == gW32PID )
    {
      if ( v9 )
      {
        v3 = __ROR8__(v9, 64 - (gCookie & 0x3Fu));
        if ( v3 != gCookie )
          vDeleteLOCALFONT((struct _LOCALFONT *)(v3 ^ gCookie));
      }
    }
  }
  v4 = HANDLE_TO_INDEX(a1);
  GdiGetEntry(v4, &v10);
  v5 = a1 | 0x800000;
  if ( (SBYTE12(v10) & 0x80u) == 0 )
    v5 = a1;
  v6 = NtGdiDeleteObjectApp(v5);
  RtlLeaveCriticalSection(&semLocal);
  return v6;
}

```

## disassembly

```asm
0x180071d50  mov     [rsp-8+arg_0], rbx
0x180071d55  push    rbp
0x180071d56  mov     rbp, rsp
0x180071d59  sub     rsp, 50h
0x180071d5d  mov     rbx, rcx
0x180071d60  xorps   xmm0, xmm0
0x180071d63  xor     eax, eax
0x180071d65  lea     rcx, semLocal; CriticalSection
0x180071d6c  movups  [rbp+var_18], xmm0
0x180071d70  mov     [rbp+var_8], rax
0x180071d74  call    cs:__imp_RtlEnterCriticalSection
0x180071d7a  mov     rcx, rbx
0x180071d7d  call    HANDLE_TO_INDEX
0x180071d82  mov     rcx, cs:__imp_gMaxGdiHandleCount
0x180071d89  cmp     eax, [rcx]
0x180071d8b  jnb     short loc_180071E0A
0x180071d8d  xor     ecx, ecx
0x180071d8f  lea     rdx, [rbp+var_30]
0x180071d93  mov     [rbp+var_20], rcx
0x180071d97  xorps   xmm0, xmm0
0x180071d9a  mov     ecx, eax
0x180071d9c  movups  [rbp+var_30], xmm0
0x180071da0  call    cs:__imp_GdiGetEntry
0x180071da6  test    eax, eax
0x180071da8  js      short loc_180071E0A
0x180071daa  cmp     byte ptr [rbp+var_30+0Eh], 0Ah
0x180071dae  jnz     short loc_180071E0A
0x180071db0  movzx   eax, byte ptr [rbp+var_30+0Ch]
0x180071db4  movzx   ecx, byte ptr [rbp+var_30+0Dh]
0x180071db8  shl     cx, 8
0x180071dbc  or      cx, ax
0x180071dbf  mov     eax, ebx
0x180071dc1  shr     eax, 10h
0x180071dc4  cmp     cx, ax
0x180071dc7  jnz     short loc_180071E0A
0x180071dc9  mov     rax, cs:__imp_gW32PID
0x180071dd0  mov     ecx, dword ptr [rbp+var_30+8]
0x180071dd3  and     ecx, 0FFFFFFFEh
0x180071dd6  cmp     ecx, [rax]
0x180071dd8  jnz     short loc_180071E0A
0x180071dda  mov     rdx, [rbp+var_20]
0x180071dde  test    rdx, rdx
0x180071de1  jz      short loc_180071E0A
0x180071de3  mov     rax, cs:__imp_gCookie
0x180071dea  mov     ecx, 40h ; '@'
0x180071def  mov     r8, [rax]
0x180071df2  mov     eax, r8d
0x180071df5  and     eax, 3Fh
0x180071df8  sub     ecx, eax
0x180071dfa  ror     rdx, cl
0x180071dfd  xor     r8, rdx
0x180071e00  jz      short loc_180071E0A
0x180071e02  mov     rcx, r8; struct _LOCALFONT *
0x180071e05  call    ?vDeleteLOCALFONT@@YAXPEAU_LOCALFONT@@@Z; vDeleteLOCALFONT(_LOCALFONT *)
0x180071e0a  mov     rcx, rbx
0x180071e0d  call    HANDLE_TO_INDEX
0x180071e12  mov     ecx, eax
0x180071e14  lea     rdx, [rbp+var_18]
0x180071e18  call    cs:__imp_GdiGetEntry
0x180071e1e  mov     rcx, rbx
0x180071e21  bts     rcx, 17h
0x180071e26  test    byte ptr [rbp+var_18+0Ch], 80h
0x180071e2a  cmovz   rcx, rbx
0x180071e2e  call    cs:__imp_NtGdiDeleteObjectApp
0x180071e34  lea     rcx, semLocal; CriticalSection
0x180071e3b  mov     ebx, eax
0x180071e3d  call    cs:__imp_RtlLeaveCriticalSection
0x180071e43  mov     eax, ebx
0x180071e45  mov     rbx, [rsp+50h+arg_0]
0x180071e4a  add     rsp, 50h
0x180071e4e  pop     rbp
0x180071e4f  retn
```
