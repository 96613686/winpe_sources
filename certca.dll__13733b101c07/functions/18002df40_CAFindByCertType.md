# CAFindByCertType

- ea: `0x18002df40`
- end: `0x18002e02a`
- name: `CAFindByCertType`
- size: `234`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180005f00`
- `0x180008420`
- `0x18002df40`
- `0x180035da8`
- `0x1800361b0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002df98`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002df98`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e00c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e00c`

## string_xrefs

- `0x18002dfad`: `(certificateTemplates=`

## pseudocode

```c
__int64 __fastcall CAFindByCertType(unsigned __int16 *a1, unsigned __int16 *a2, unsigned int a3, struct CCAInfo **a4)
{
  __int64 v9; // rax
  unsigned __int64 v10; // r14
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // rdi
  unsigned int v13; // ebx
  unsigned int DnsDomain; // eax

  if ( !a1 || !a4 )
    return 2147500035LL;
  if ( (a3 & 0x1000) != 0 )
    return 2147500033LL;
  v9 = -1;
  do
    ++v9;
  while ( a1[v9] );
  v10 = v9 + 24;
  v11 = (unsigned __int16 *)LocalAlloc(0, 2 * (v9 + 24));
  v12 = v11;
  if ( v11 )
  {
    StringCchCopyW(v11, v10, L"(certificateTemplates=");
    StringCchCatW(v12, v10, a1);
    StringCchCatW(v12, v10, L")");
    if ( (a3 & 1) != 0 )
      DnsDomain = CCAInfo::FindDnsDomain(v12, a2, a3, a4);
    else
      DnsDomain = CCAInfo::Find(v12, (LDAP *)a2, a3, a4);
    v13 = DnsDomain;
    if ( !*a4 )
      v13 = -2147023728;
    LocalFree(v12);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v13;
}

```

## disassembly

```asm
0x18002df40  push    rbx
0x18002df42  push    rbp
0x18002df43  push    rsi
0x18002df44  push    rdi
0x18002df45  push    r12
0x18002df47  push    r14
0x18002df49  push    r15
0x18002df4b  sub     rsp, 20h
0x18002df4f  xor     r12d, r12d
0x18002df52  mov     rsi, r9
0x18002df55  mov     ebx, r8d
0x18002df58  mov     r15, rdx
0x18002df5b  mov     rbp, rcx
0x18002df5e  test    rcx, rcx
0x18002df61  jz      loc_18002E016
0x18002df67  test    r9, r9
0x18002df6a  jz      loc_18002E016
0x18002df70  bt      ebx, 0Ch
0x18002df74  jnb     short loc_18002DF80
0x18002df76  mov     eax, 80004001h
0x18002df7b  jmp     loc_18002E01B
0x18002df80  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002df84  inc     rax
0x18002df87  cmp     [rcx+rax*2], r12w
0x18002df8c  jnz     short loc_18002DF84
0x18002df8e  lea     r14, [rax+18h]
0x18002df92  xor     ecx, ecx; uFlags
0x18002df94  lea     rdx, [r14+r14]; uBytes
0x18002df98  call    cs:__imp_LocalAlloc
0x18002df9e  mov     rdi, rax
0x18002dfa1  test    rax, rax
0x18002dfa4  jnz     short loc_18002DFAD
0x18002dfa6  mov     ebx, 8007000Eh
0x18002dfab  jmp     short loc_18002E012
0x18002dfad  lea     r8, aCertificatetem_0; "(certificateTemplates="
0x18002dfb4  mov     rdx, r14; unsigned __int64
0x18002dfb7  mov     rcx, rdi; unsigned __int16 *
0x18002dfba  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002dfbf  mov     r8, rbp; unsigned __int16 *
0x18002dfc2  mov     rdx, r14; unsigned __int64
0x18002dfc5  mov     rcx, rdi; unsigned __int16 *
0x18002dfc8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002dfcd  lea     r8, asc_1800B3FAC; ")"
0x18002dfd4  mov     rdx, r14; unsigned __int64
0x18002dfd7  mov     rcx, rdi; unsigned __int16 *
0x18002dfda  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002dfdf  mov     r9, rsi; struct CCAInfo **
0x18002dfe2  mov     r8d, ebx; unsigned int
0x18002dfe5  mov     rdx, r15; unsigned __int16 *
0x18002dfe8  mov     rcx, rdi; unsigned __int16 *
0x18002dfeb  test    bl, 1
0x18002dfee  jz      short loc_18002DFF7
0x18002dff0  call    ?FindDnsDomain@CCAInfo@@SAJPEBG0KPEAPEAV1@@Z; CCAInfo::FindDnsDomain(ushort const *,ushort const *,ulong,CCAInfo * *)
0x18002dff5  jmp     short loc_18002DFFC
0x18002dff7  call    ?Find@CCAInfo@@SAJPEBG0KPEAPEAV1@@Z; CCAInfo::Find(ushort const *,ushort const *,ulong,CCAInfo * *)
0x18002dffc  cmp     [rsi], r12
0x18002dfff  mov     ebx, eax
0x18002e001  mov     eax, 80070490h
0x18002e006  cmovz   ebx, eax
0x18002e009  mov     rcx, rdi; hMem
0x18002e00c  call    cs:__imp_LocalFree
0x18002e012  mov     eax, ebx
0x18002e014  jmp     short loc_18002E01B
0x18002e016  mov     eax, 80004003h
0x18002e01b  add     rsp, 20h
0x18002e01f  pop     r15
0x18002e021  pop     r14
0x18002e023  pop     r12
0x18002e025  pop     rdi
0x18002e026  pop     rsi
0x18002e027  pop     rbp
0x18002e028  pop     rbx
0x18002e029  retn
```
