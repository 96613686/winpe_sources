# TInstalledDriverScorer::ComputeScore(_SP_DRVINFO_DATA_V2_W const *,_SP_DRVINFO_DETAIL_DATA_W const *,ulong,ushort *)

- ea: `0x180024240`
- end: `0x18002436a`
- name: `?ComputeScore@TInstalledDriverScorer@@UEBAKPEBU_SP_DRVINFO_DATA_V2_W@@PEBU_SP_DRVINFO_DETAIL_DATA_W@@KPEAG@Z`
- size: `298`
- prototype: `unsigned int __usercall@<eax>(TInstalledDriverScorer *__hidden this@<rcx>, const struct _SP_DRVINFO_DATA_V2_W *@<rdx>, const struct _SP_DRVINFO_DETAIL_DATA_W *@<r8>, unsigned int@<r9d>, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180024240`
- `0x180024a4c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180024334`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180024334`
- `KERNEL32!lstrcmpiW` at `0x1800242d3`
- `KERNEL32!lstrcmpiW` at `0x1800242f4`
- `KERNEL32!lstrcmpiW` at `0x180024318`
- `KERNEL32!lstrcmpiW` at `0x1800242d3`
- `KERNEL32!lstrcmpiW` at `0x1800242f4`
- `KERNEL32!lstrcmpiW` at `0x180024318`

## pseudocode

```c
__int64 __fastcall TInstalledDriverScorer::ComputeScore(
        TInstalledDriverScorer *this,
        const struct _SP_DRVINFO_DATA_V2_W *a2,
        const struct _SP_DRVINFO_DETAIL_DATA_W *a3,
        unsigned int a4,
        unsigned __int16 *a5)
{
  bool v5; // zf
  unsigned int v8; // edx
  int HardwareIdIndex; // eax
  int v10; // ebx
  int v11; // ebx
  unsigned int v12; // ebx
  const WCHAR *v13; // rcx
  const WCHAR *v14; // rcx
  const WCHAR *v15; // rcx
  LONG v16; // eax
  int v18; // [rsp+50h] [rbp+18h] BYREF

  v5 = a3->CompatIDsOffset == 0;
  v18 = 0;
  if ( !v5 || a3->CompatIDsLength )
  {
    HardwareIdIndex = TDriverScorer::GetHardwareIdIndex(this, a3->HardwareID, a4, a5, &v18);
    v8 = -1;
    v10 = HardwareIdIndex;
    if ( HardwareIdIndex >= 0 )
    {
      if ( (unsigned int)HardwareIdIndex > 0x3FFFFFF )
        v10 = 0x3FFFFFF;
      v11 = 32 * v10;
      if ( v18 )
        v12 = v11 & 0x7FFFFFFF;
      else
        v12 = v11 | 0x80000000;
      v13 = *(const WCHAR **)(*((_QWORD *)this + 1) + 8LL);
      if ( v13 && lstrcmpiW(v13, a2->Description) )
        v12 |= 0x10u;
      v14 = *(const WCHAR **)(*((_QWORD *)this + 1) + 104LL);
      if ( v14 && lstrcmpiW(v14, a2->MfgName) )
        v12 |= 8u;
      v15 = *(const WCHAR **)(*((_QWORD *)this + 1) + 128LL);
      if ( v15 && lstrcmpiW(v15, a2->ProviderName) )
        v12 |= 4u;
      v16 = CompareFileTime((const FILETIME *)(*((_QWORD *)this + 1) + 88LL), &a2->DriverDate);
      v8 = v12 | 2;
      if ( v16 <= 0 )
        v8 = v12;
      if ( *(_QWORD *)(*((_QWORD *)this + 1) + 96LL) > a2->DriverVersion )
        v8 |= 1u;
    }
  }
  else
  {
    return (unsigned int)-1;
  }
  return v8;
}

```

## disassembly

```asm
0x180024240  mov     [rsp+arg_0], rbx
0x180024245  mov     [rsp+arg_8], rsi
0x18002424a  push    rdi
0x18002424b  sub     rsp, 30h
0x18002424f  cmp     dword ptr [r8+0Ch], 0
0x180024254  mov     eax, r9d
0x180024257  mov     rsi, rdx
0x18002425a  mov     [rsp+38h+arg_10], 0
0x180024262  mov     rdi, rcx
0x180024265  jnz     short loc_180024276
0x180024267  cmp     dword ptr [r8+10h], 0
0x18002426c  jnz     short loc_180024276
0x18002426e  or      edx, 0FFFFFFFFh
0x180024271  jmp     loc_180024358
0x180024276  mov     r9, [rsp+38h+arg_20]; unsigned __int16 *
0x18002427b  lea     rcx, [rsp+38h+arg_10]
0x180024280  mov     [rsp+38h+var_18], rcx; int *
0x180024285  lea     rdx, [r8+628h]; unsigned __int16 *
0x18002428c  mov     rcx, rdi; this
0x18002428f  mov     r8d, eax; unsigned int
0x180024292  call    ?GetHardwareIdIndex@TDriverScorer@@IEBAHPEBGKPEAGPEAH@Z; TDriverScorer::GetHardwareIdIndex(ushort const *,ulong,ushort *,int *)
0x180024297  or      edx, 0FFFFFFFFh
0x18002429a  mov     ebx, eax
0x18002429c  test    eax, eax
0x18002429e  js      loc_180024358
0x1800242a4  mov     eax, 3FFFFFFh
0x1800242a9  cmp     ebx, eax
0x1800242ab  cmova   ebx, eax
0x1800242ae  shl     ebx, 5
0x1800242b1  cmp     [rsp+38h+arg_10], 0
0x1800242b6  jnz     short loc_1800242BE
0x1800242b8  bts     ebx, 1Fh
0x1800242bc  jmp     short loc_1800242C2
0x1800242be  btr     ebx, 1Fh
0x1800242c2  mov     rax, [rdi+8]
0x1800242c6  mov     rcx, [rax+8]; lpString1
0x1800242ca  test    rcx, rcx
0x1800242cd  jz      short loc_1800242E0
0x1800242cf  lea     rdx, [rsi+10h]; lpString2
0x1800242d3  call    cs:__imp_lstrcmpiW
0x1800242d9  test    eax, eax
0x1800242db  jz      short loc_1800242E0
0x1800242dd  or      ebx, 10h
0x1800242e0  mov     rax, [rdi+8]
0x1800242e4  mov     rcx, [rax+68h]; lpString1
0x1800242e8  test    rcx, rcx
0x1800242eb  jz      short loc_180024301
0x1800242ed  lea     rdx, [rsi+210h]; lpString2
0x1800242f4  call    cs:__imp_lstrcmpiW
0x1800242fa  test    eax, eax
0x1800242fc  jz      short loc_180024301
0x1800242fe  or      ebx, 8
0x180024301  mov     rax, [rdi+8]
0x180024305  mov     rcx, [rax+80h]; lpString1
0x18002430c  test    rcx, rcx
0x18002430f  jz      short loc_180024325
0x180024311  lea     rdx, [rsi+410h]; lpString2
0x180024318  call    cs:__imp_lstrcmpiW
0x18002431e  test    eax, eax
0x180024320  jz      short loc_180024325
0x180024322  or      ebx, 4
0x180024325  mov     rcx, [rdi+8]
0x180024329  lea     rdx, [rsi+610h]; lpFileTime2
0x180024330  add     rcx, 58h ; 'X'; lpFileTime1
0x180024334  call    cs:__imp_CompareFileTime
0x18002433a  mov     rcx, [rdi+8]
0x18002433e  mov     edx, ebx
0x180024340  or      edx, 2
0x180024343  test    eax, eax
0x180024345  mov     rax, [rsi+618h]
0x18002434c  cmovle  edx, ebx
0x18002434f  cmp     [rcx+60h], rax
0x180024353  jbe     short loc_180024358
0x180024355  or      edx, 1
0x180024358  mov     rbx, [rsp+38h+arg_0]
0x18002435d  mov     eax, edx
0x18002435f  mov     rsi, [rsp+38h+arg_8]
0x180024364  add     rsp, 30h
0x180024368  pop     rdi
0x180024369  retn
```
