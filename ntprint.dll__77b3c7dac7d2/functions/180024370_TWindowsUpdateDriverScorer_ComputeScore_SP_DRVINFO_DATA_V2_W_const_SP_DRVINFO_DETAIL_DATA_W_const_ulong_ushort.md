# TWindowsUpdateDriverScorer::ComputeScore(_SP_DRVINFO_DATA_V2_W const *,_SP_DRVINFO_DETAIL_DATA_W const *,ulong,ushort *)

- ea: `0x180024370`
- end: `0x1800244e3`
- name: `?ComputeScore@TWindowsUpdateDriverScorer@@UEBAKPEBU_SP_DRVINFO_DATA_V2_W@@PEBU_SP_DRVINFO_DETAIL_DATA_W@@KPEAG@Z`
- size: `371`
- prototype: `unsigned int __usercall@<eax>(TWindowsUpdateDriverScorer *__hidden this@<rcx>, const struct _SP_DRVINFO_DATA_V2_W *@<rdx>, const struct _SP_DRVINFO_DETAIL_DATA_W *@<r8>, unsigned int@<r9d>, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180007944`
- `0x180024370`
- `0x180024a4c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800244ae`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800244ae`
- `KERNEL32!lstrcmpiW` at `0x18002439a`
- `KERNEL32!lstrcmpiW` at `0x18002446e`
- `KERNEL32!lstrcmpiW` at `0x180024492`
- `KERNEL32!lstrcmpiW` at `0x18002439a`
- `KERNEL32!lstrcmpiW` at `0x18002446e`
- `KERNEL32!lstrcmpiW` at `0x180024492`

## pseudocode

```c
__int64 __fastcall TWindowsUpdateDriverScorer::ComputeScore(
        TWindowsUpdateDriverScorer *this,
        const struct _SP_DRVINFO_DATA_V2_W *a2,
        const struct _SP_DRVINFO_DETAIL_DATA_W *a3,
        unsigned int a4,
        unsigned __int16 *a5)
{
  unsigned __int64 v6; // r15
  const WCHAR *v9; // rcx
  BOOL v10; // ebp
  int v11; // r14d
  WCHAR *HardwareID; // rbx
  int v13; // r11d
  int v14; // eax
  int HardwareIdIndex; // eax
  unsigned int v16; // edx
  int v17; // r11d
  unsigned int v18; // ebx
  const WCHAR *v19; // rcx
  const WCHAR *v20; // rcx
  LONG v21; // eax
  int v23; // [rsp+70h] [rbp+8h] BYREF

  v6 = a4;
  v9 = *(const WCHAR **)(*((_QWORD *)this + 1) + 8LL);
  v10 = v9 && !lstrcmpiW(v9, a2->Description);
  v11 = 0;
  v23 = 0;
  if ( a3->CompatIDsOffset || a3->CompatIDsLength )
  {
    HardwareID = a3->HardwareID;
    HardwareIdIndex = TDriverScorer::GetHardwareIdIndex(this, HardwareID, v6, a5, &v23);
    v11 = v23;
    v13 = HardwareIdIndex;
    v14 = 1;
  }
  else
  {
    HardwareID = a3->HardwareID;
    v13 = -1;
    v14 = 0;
  }
  if ( v10 )
  {
    if ( v14 && v13 < 0 )
      StringCchCopyW(a5, v6, HardwareID);
  }
  else
  {
    v16 = -1;
    if ( v13 < 0 )
      return v16;
  }
  if ( (unsigned int)v13 > 0x3FFFFFF )
    v13 = 0x3FFFFFF;
  v17 = 4 * (v13 & 0x3FFFFFF);
  if ( !v11 )
    v17 |= 0x10000000u;
  v18 = v17 | 0x80000000;
  v19 = *(const WCHAR **)(*((_QWORD *)this + 1) + 104LL);
  if ( v10 )
    v18 = v17;
  if ( v19 && lstrcmpiW(v19, a2->MfgName) )
    v18 |= 2u;
  v20 = *(const WCHAR **)(*((_QWORD *)this + 1) + 128LL);
  if ( v20 && lstrcmpiW(v20, a2->ProviderName) )
    v18 |= 1u;
  v21 = CompareFileTime((const FILETIME *)(*((_QWORD *)this + 1) + 88LL), &a2->DriverDate);
  v16 = v18 | 0x40000000;
  if ( v21 <= 0 )
    v16 = v18;
  if ( *(_QWORD *)(*((_QWORD *)this + 1) + 96LL) > a2->DriverVersion )
    v16 |= 0x20000000u;
  return v16;
}

```

## disassembly

```asm
0x180024370  push    rbx
0x180024372  push    rbp
0x180024373  push    rsi
0x180024374  push    rdi
0x180024375  push    r14
0x180024377  push    r15
0x180024379  sub     rsp, 38h
0x18002437d  mov     rax, [rcx+8]
0x180024381  mov     rdi, rcx
0x180024384  mov     r15d, r9d
0x180024387  mov     rbx, r8
0x18002438a  mov     rsi, rdx
0x18002438d  mov     rcx, [rax+8]; lpString1
0x180024391  test    rcx, rcx
0x180024394  jz      short loc_1800243A9
0x180024396  add     rdx, 10h; lpString2
0x18002439a  call    cs:__imp_lstrcmpiW
0x1800243a0  test    eax, eax
0x1800243a2  jnz     short loc_1800243A9
0x1800243a4  lea     ebp, [rax+1]
0x1800243a7  jmp     short loc_1800243AB
0x1800243a9  xor     ebp, ebp
0x1800243ab  xor     r14d, r14d
0x1800243ae  mov     [rsp+68h+arg_0], r14d
0x1800243b3  cmp     [rbx+0Ch], r14d
0x1800243b7  jnz     short loc_1800243CE
0x1800243b9  cmp     [rbx+10h], r14d
0x1800243bd  jnz     short loc_1800243CE
0x1800243bf  add     rbx, 628h
0x1800243c6  or      r11d, 0FFFFFFFFh
0x1800243ca  xor     eax, eax
0x1800243cc  jmp     short loc_180024402
0x1800243ce  mov     r9, [rsp+68h+arg_20]; unsigned __int16 *
0x1800243d6  lea     rax, [rsp+68h+arg_0]
0x1800243db  add     rbx, 628h
0x1800243e2  mov     [rsp+68h+var_48], rax; int *
0x1800243e7  mov     rdx, rbx; unsigned __int16 *
0x1800243ea  mov     r8d, r15d; unsigned int
0x1800243ed  mov     rcx, rdi; this
0x1800243f0  call    ?GetHardwareIdIndex@TDriverScorer@@IEBAHPEBGKPEAGPEAH@Z; TDriverScorer::GetHardwareIdIndex(ushort const *,ulong,ushort *,int *)
0x1800243f5  mov     r14d, [rsp+68h+arg_0]
0x1800243fa  mov     r11d, eax
0x1800243fd  mov     eax, 1
0x180024402  test    ebp, ebp
0x180024404  jnz     short loc_180024414
0x180024406  or      edx, 0FFFFFFFFh
0x180024409  test    r11d, r11d
0x18002440c  js      loc_1800244D4
0x180024412  jmp     short loc_180024430
0x180024414  test    eax, eax
0x180024416  jz      short loc_180024430
0x180024418  test    r11d, r11d
0x18002441b  jns     short loc_180024430
0x18002441d  mov     rcx, [rsp+68h+arg_20]; unsigned __int16 *
0x180024425  mov     rdx, r15; unsigned __int64
0x180024428  mov     r8, rbx; unsigned __int16 *
0x18002442b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180024430  mov     eax, 3FFFFFFh
0x180024435  cmp     r11d, eax
0x180024438  cmova   r11d, eax
0x18002443c  and     r11d, eax
0x18002443f  shl     r11d, 2
0x180024443  test    r14d, r14d
0x180024446  jnz     short loc_18002444D
0x180024448  bts     r11d, 1Ch
0x18002444d  mov     rax, [rdi+8]
0x180024451  mov     ebx, r11d
0x180024454  bts     ebx, 1Fh
0x180024458  test    ebp, ebp
0x18002445a  mov     rcx, [rax+68h]; lpString1
0x18002445e  cmovnz  ebx, r11d
0x180024462  test    rcx, rcx
0x180024465  jz      short loc_18002447B
0x180024467  lea     rdx, [rsi+210h]; lpString2
0x18002446e  call    cs:__imp_lstrcmpiW
0x180024474  test    eax, eax
0x180024476  jz      short loc_18002447B
0x180024478  or      ebx, 2
0x18002447b  mov     rax, [rdi+8]
0x18002447f  mov     rcx, [rax+80h]; lpString1
0x180024486  test    rcx, rcx
0x180024489  jz      short loc_18002449F
0x18002448b  lea     rdx, [rsi+410h]; lpString2
0x180024492  call    cs:__imp_lstrcmpiW
0x180024498  test    eax, eax
0x18002449a  jz      short loc_18002449F
0x18002449c  or      ebx, 1
0x18002449f  mov     rcx, [rdi+8]
0x1800244a3  lea     rdx, [rsi+610h]; lpFileTime2
0x1800244aa  add     rcx, 58h ; 'X'; lpFileTime1
0x1800244ae  call    cs:__imp_CompareFileTime
0x1800244b4  mov     rcx, [rdi+8]
0x1800244b8  mov     edx, ebx
0x1800244ba  bts     edx, 1Eh
0x1800244be  test    eax, eax
0x1800244c0  mov     rax, [rsi+618h]
0x1800244c7  cmovle  edx, ebx
0x1800244ca  cmp     [rcx+60h], rax
0x1800244ce  jbe     short loc_1800244D4
0x1800244d0  bts     edx, 1Dh
0x1800244d4  mov     eax, edx
0x1800244d6  add     rsp, 38h
0x1800244da  pop     r15
0x1800244dc  pop     r14
0x1800244de  pop     rdi
0x1800244df  pop     rsi
0x1800244e0  pop     rbp
0x1800244e1  pop     rbx
0x1800244e2  retn
```
