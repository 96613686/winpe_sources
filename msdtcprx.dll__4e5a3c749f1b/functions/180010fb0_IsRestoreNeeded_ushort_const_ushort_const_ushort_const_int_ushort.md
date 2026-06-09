# IsRestoreNeeded(ushort const *,ushort const *,ushort const *,int *,ushort * *)

- ea: `0x180010fb0`
- end: `0x180011319`
- name: `?IsRestoreNeeded@@YAJPEBG00PEAHPEAPEAG@Z`
- size: `873`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18007182c`

## callees

- `0x180003cf0`
- `0x18000d5f4`
- `0x180010fb0`
- `0x18001156c`
- `0x18001d138`
- `0x18001d178`
- `0x180071910`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800112a7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800112a7`

## string_xrefs

- `0x18001128d`: `ReadRegKeyValue32W(pwszMsdtcRestoreKey) to get value failed`
- `0x18001116d`: `ReadRegKeyValue32W(pwszRestoreKey) to get value failed`
- `0x1800111ce`: `IsRestoreNeeded, ReadRegKeyValue32W(pwszMsdtcRestoreKey) to get size failed`
- `0x18001115c`: `IsRestoreNeeded, ReadRegKeyValue32W(pwszRestoreKey) to get value failed`
- `0x1800111df`: `ReadRegKeyValue32W(pwszMsdtcRestoreKey) to get size failed`
- `0x1800110a3`: `ReadRegKeyValue32W(pwszRestoreKey) to get size failed`
- `0x18001127c`: `IsRestoreNeeded, ReadRegKeyValue32W(pwszMsdtcRestoreKey) to get value failed`
- `0x180011092`: `IsRestoreNeeded, ReadRegKeyValue32W(pwszRestoreKey) to get size failed`
- `0x180010ff3`: `com\complus\dtc\shared\util\vssbackup.cpp`
- `0x180011036`: `IsRestoreNeeded (com\complus\dtc\shared\util\vssbackup.cpp@46): IsRestoreNeeded, pbRestoreNeeded`

## pseudocode

```c
__int64 __fastcall IsRestoreNeeded(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int *a4)
{
  HKEY v5; // rcx
  const unsigned __int16 *v6; // r8
  unsigned __int8 *v7; // rsi
  int v8; // eax
  unsigned int v9; // ebx
  unsigned __int8 *v10; // rbp
  BOOL v11; // edi
  const wchar_t *v12; // rax
  __int64 v13; // r9
  HKEY v14; // rcx
  const unsigned __int16 *v15; // r8
  int v16; // eax
  HKEY v17; // rcx
  const unsigned __int16 *v18; // r8
  int v19; // eax
  HKEY v20; // rcx
  const unsigned __int16 *v21; // r8
  int v22; // eax
  __int64 v24; // [rsp+28h] [rbp-50h]
  const wchar_t *v25; // [rsp+30h] [rbp-48h]
  __int64 v26; // [rsp+38h] [rbp-40h]
  unsigned int Size; // [rsp+90h] [rbp+18h] BYREF
  int Size_4; // [rsp+94h] [rbp+1Ch]

  Size_4 = HIDWORD(a3);
  Size = 0;
  TraceStringInline(
    17,
    6,
    L"com\\complus\\dtc\\shared\\util\\vssbackup.cpp",
    43,
    L"IsRestoreNeeded",
    0,
    L"In, pwszRestoreKey = %ws, pwszMsdtcRestoreKey = %ws, pwszRestoreValue = %ws",
    L"SOFTWARE\\MICROSOFT\\WINDOWS NT\\CurrentVersion\\ASR\\RestoreSession",
    L"SYSTEM\\CurrentControlSet\\Control\\MSDTC\\ASR\\RestoreSession",
    L"LastInstance");
  if ( !a4 )
    DtcInternalErrorW(L"IsRestoreNeeded (com\\complus\\dtc\\shared\\util\\vssbackup.cpp@46): IsRestoreNeeded, pbRestoreNeeded");
  v7 = 0;
  *a4 = 0;
  v8 = ReadRegKeyValue32W(v5, L"SOFTWARE\\MICROSOFT\\WINDOWS NT\\CurrentVersion\\ASR\\RestoreSession", v6, 0, &Size);
  v9 = v8;
  if ( !v8 )
    goto LABEL_12;
  v10 = 0;
  if ( v8 != 2 )
  {
    if ( v8 != 234 )
    {
      if ( v8 > 0 )
        v9 = (unsigned __int16)v8 | 0x80070000;
      TraceFileW(
        v9,
        L"IsRestoreNeeded, ReadRegKeyValue32W(pwszRestoreKey) to get size failed",
        L"com\\complus\\dtc\\shared\\util\\vssbackup.cpp",
        0x44u);
      v12 = L"ReadRegKeyValue32W(pwszRestoreKey) to get size failed";
      v13 = 69;
LABEL_10:
      v25 = v12;
      LODWORD(v24) = v9;
LABEL_11:
      TraceStringInline(17, 1, L"com\\complus\\dtc\\shared\\util\\vssbackup.cpp", v13, L"IsRestoreNeeded", v24, v25);
      v11 = 0;
      goto LABEL_34;
    }
LABEL_12:
    v10 = (unsigned __int8 *)operator new(Size);
    if ( !v10 )
    {
      v9 = -2147024882;
      TraceFileW(
        -2147024882,
        L"IsRestoreNeeded, new BYTE[cbSizeOfData] failed",
        L"com\\complus\\dtc\\shared\\util\\vssbackup.cpp",
        0x4Eu);
      v25 = L"new BYTE[cbSizeOfData] failed";
      v13 = 79;
      LODWORD(v24) = -2147024882;
      goto LABEL_11;
    }
    v16 = ReadRegKeyValue32W(
            v14,
            L"SOFTWARE\\MICROSOFT\\WINDOWS NT\\CurrentVersion\\ASR\\RestoreSession",
            v15,
            v10,
            &Size);
    v9 = v16;
    if ( v16 )
    {
      if ( v16 == 2 )
        goto LABEL_5;
      if ( v16 > 0 )
        v9 = (unsigned __int16)v16 | 0x80070000;
      TraceFileW(
        v9,
        L"IsRestoreNeeded, ReadRegKeyValue32W(pwszRestoreKey) to get value failed",
        L"com\\complus\\dtc\\shared\\util\\vssbackup.cpp",
        0x61u);
      v12 = L"ReadRegKeyValue32W(pwszRestoreKey) to get value failed";
      v13 = 98;
      goto LABEL_10;
    }
    Size = 0;
    v19 = ReadRegKeyValue32W(v17, L"SYSTEM\\CurrentControlSet\\Control\\MSDTC\\ASR\\RestoreSession", v18, 0, &Size);
    v9 = v19;
    if ( v19 )
    {
      if ( v19 == 2 )
        goto LABEL_21;
      if ( v19 != 234 )
      {
        if ( v19 > 0 )
          v9 = (unsigned __int16)v19 | 0x80070000;
        TraceFileW(
          v9,
          L"IsRestoreNeeded, ReadRegKeyValue32W(pwszMsdtcRestoreKey) to get size failed",
          L"com\\complus\\dtc\\shared\\util\\vssbackup.cpp",
          0x79u);
        v12 = L"ReadRegKeyValue32W(pwszMsdtcRestoreKey) to get size failed";
        v13 = 122;
        goto LABEL_10;
      }
    }
    v7 = (unsigned __int8 *)operator new(Size);
    if ( !v7 )
    {
      v9 = -2147024882;
      TraceFileW(
        -2147024882,
        L"IsRestoreNeeded, new BYTE[cbSizeOfData] failed",
        L"com\\complus\\dtc\\shared\\util\\vssbackup.cpp",
        0x83u);
      v13 = 132;
      v25 = L"new BYTE[cbSizeOfData] failed";
      LODWORD(v24) = -2147024882;
      goto LABEL_11;
    }
    v22 = ReadRegKeyValue32W(v20, L"SYSTEM\\CurrentControlSet\\Control\\MSDTC\\ASR\\RestoreSession", v21, v7, &Size);
    v9 = v22;
    if ( !v22 )
    {
      v9 = 0;
      v11 = lstrcmpiW((LPCWSTR)v10, (LPCWSTR)v7) != 0;
      goto LABEL_34;
    }
    if ( v22 != 2 )
    {
      if ( v22 > 0 )
        v9 = (unsigned __int16)v22 | 0x80070000;
      TraceFileW(
        v9,
        L"IsRestoreNeeded, ReadRegKeyValue32W(pwszMsdtcRestoreKey) to get value failed",
        L"com\\complus\\dtc\\shared\\util\\vssbackup.cpp",
        0x96u);
      v12 = L"ReadRegKeyValue32W(pwszMsdtcRestoreKey) to get value failed";
      v13 = 151;
      goto LABEL_10;
    }
LABEL_21:
    v9 = 0;
    v11 = 1;
    goto LABEL_34;
  }
LABEL_5:
  v9 = 0;
  v11 = 0;
LABEL_34:
  *a4 = v11;
  operator delete(v10);
  operator delete(v7);
  LODWORD(v26) = v11;
  LODWORD(v24) = v9;
  TraceStringInline(
    17,
    6,
    L"com\\complus\\dtc\\shared\\util\\vssbackup.cpp",
    183,
    L"IsRestoreNeeded",
    v24,
    L"Out, bRestoreNeeded = %d",
    v26);
  return v9;
}

```

## disassembly

```asm
0x180010fb0  mov     r11, rsp
0x180010fb3  mov     [r11+8], rbx
0x180010fb7  mov     [r11+10h], rbp
0x180010fbb  mov     [r11+18h], r8
0x180010fbf  push    rsi
0x180010fc0  push    rdi
0x180010fc1  push    r12
0x180010fc3  push    r13
0x180010fc5  push    r14
0x180010fc7  sub     rsp, 50h
0x180010fcb  lea     rax, aLastinstance; "LastInstance"
0x180010fd2  mov     dword ptr [r11+18h], 0
0x180010fda  mov     [r11-30h], rax
0x180010fde  lea     r13, aSoftwareMicros_6; "SOFTWARE\\MICROSOFT\\WINDOWS NT\\Curren"...
0x180010fe5  mov     r14, r9
0x180010fe8  lea     rax, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\MSD"...
0x180010fef  mov     [r11-38h], rax
0x180010ff3  lea     r12, aComComplusDtcS_8; "com\\complus\\dtc\\shared\\util\\vssbac"...
0x180010ffa  mov     [r11-40h], r13
0x180010ffe  lea     rax, aInPwszrestorek; "In, pwszRestoreKey = %ws, pwszMsdtcRest"...
0x180011005  mov     [r11-48h], rax
0x180011009  mov     r9d, 2Bh ; '+'
0x18001100f  lea     rax, aIsrestoreneede_0; "IsRestoreNeeded"
0x180011016  mov     qword ptr [r11-50h], 0
0x18001101e  mov     r8, r12
0x180011021  mov     [r11-58h], rax
0x180011025  lea     edx, [r9-25h]
0x180011029  lea     ecx, [rdx+0Bh]
0x18001102c  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180011031  test    r14, r14
0x180011034  jnz     short loc_180011043
0x180011036  lea     rcx, aIsrestoreneede_5; "IsRestoreNeeded (com\\complus\\dtc\\sha"...
0x18001103d  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180011043  lea     rax, [rsp+78h+Size]
0x18001104b  xor     esi, esi
0x18001104d  xor     r9d, r9d; unsigned __int8 *
0x180011050  mov     [r14], esi
0x180011053  mov     rdx, r13; unsigned __int16 *
0x180011056  mov     [rsp+78h+var_58], rax; unsigned int *
0x18001105b  call    ?ReadRegKeyValue32W@@YAJPEAUHKEY__@@PEBG1PEAEPEAK@Z; ReadRegKeyValue32W(HKEY__ *,ushort const *,ushort const *,uchar *,ulong *)
0x180011060  mov     ebx, eax
0x180011062  mov     edi, 0EAh
0x180011067  test    eax, eax
0x180011069  jz      short loc_1800110DC
0x18001106b  xor     ebp, ebp
0x18001106d  cmp     eax, 2
0x180011070  jnz     short loc_18001107B
0x180011072  xor     ebx, ebx
0x180011074  xor     edi, edi
0x180011076  jmp     loc_1800112B5
0x18001107b  cmp     eax, edi
0x18001107d  jz      short loc_1800110DC
0x18001107f  test    eax, eax
0x180011081  jle     short loc_18001108C
0x180011083  movzx   ebx, ax
0x180011086  or      ebx, 80070000h
0x18001108c  mov     r9d, 44h ; 'D'; unsigned int
0x180011092  lea     rdx, aIsrestoreneede_2; "IsRestoreNeeded, ReadRegKeyValue32W(pws"...
0x180011099  mov     r8, r12; unsigned __int16 *
0x18001109c  mov     ecx, ebx; int
0x18001109e  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x1800110a3  lea     rax, aReadregkeyvalu_1; "ReadRegKeyValue32W(pwszRestoreKey) to g"...
0x1800110aa  mov     r9d, 45h ; 'E'
0x1800110b0  mov     [rsp+78h+var_48], rax
0x1800110b5  mov     dword ptr [rsp+78h+var_50], ebx
0x1800110b9  mov     edx, 1
0x1800110be  lea     r13, aIsrestoreneede_0; "IsRestoreNeeded"
0x1800110c5  mov     r8, r12
0x1800110c8  mov     [rsp+78h+var_58], r13
0x1800110cd  lea     ecx, [rdx+10h]
0x1800110d0  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800110d5  xor     edi, edi
0x1800110d7  jmp     loc_1800112BC
0x1800110dc  mov     ecx, dword ptr [rsp+78h+Size]; Size
0x1800110e3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800110e8  mov     rbp, rax
0x1800110eb  test    rax, rax
0x1800110ee  jnz     short loc_180011122
0x1800110f0  mov     edi, 8007000Eh
0x1800110f5  lea     r9d, [rax+4Eh]; unsigned int
0x1800110f9  mov     ecx, edi; int
0x1800110fb  lea     rdx, aIsrestoreneede_4; "IsRestoreNeeded, new BYTE[cbSizeOfData]"...
0x180011102  mov     r8, r12; unsigned __int16 *
0x180011105  mov     ebx, edi
0x180011107  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x18001110c  lea     rax, aNewByteCbsizeo; "new BYTE[cbSizeOfData] failed"
0x180011113  mov     [rsp+78h+var_48], rax
0x180011118  lea     r9d, [rbp+4Fh]
0x18001111c  mov     dword ptr [rsp+78h+var_50], edi
0x180011120  jmp     short loc_1800110B9
0x180011122  lea     rax, [rsp+78h+Size]
0x18001112a  mov     r9, rbp; unsigned __int8 *
0x18001112d  mov     rdx, r13; unsigned __int16 *
0x180011130  mov     [rsp+78h+var_58], rax; unsigned int *
0x180011135  call    ?ReadRegKeyValue32W@@YAJPEAUHKEY__@@PEBG1PEAEPEAK@Z; ReadRegKeyValue32W(HKEY__ *,ushort const *,ushort const *,uchar *,ulong *)
0x18001113a  mov     ebx, eax
0x18001113c  test    eax, eax
0x18001113e  jz      short loc_18001117F
0x180011140  cmp     eax, 2
0x180011143  jz      loc_180011072
0x180011149  test    eax, eax
0x18001114b  jle     short loc_180011156
0x18001114d  movzx   ebx, ax
0x180011150  or      ebx, 80070000h
0x180011156  mov     r9d, 61h ; 'a'; unsigned int
0x18001115c  lea     rdx, aIsrestoreneede_1; "IsRestoreNeeded, ReadRegKeyValue32W(pws"...
0x180011163  mov     r8, r12; unsigned __int16 *
0x180011166  mov     ecx, ebx; int
0x180011168  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x18001116d  lea     rax, aReadregkeyvalu_0; "ReadRegKeyValue32W(pwszRestoreKey) to g"...
0x180011174  mov     r9d, 62h ; 'b'
0x18001117a  jmp     loc_1800110B0
0x18001117f  lea     rax, [rsp+78h+Size]
0x180011187  mov     dword ptr [rsp+78h+Size], esi
0x18001118e  xor     r9d, r9d; unsigned __int8 *
0x180011191  mov     [rsp+78h+var_58], rax; unsigned int *
0x180011196  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\MSD"...
0x18001119d  call    ?ReadRegKeyValue32W@@YAJPEAUHKEY__@@PEBG1PEAEPEAK@Z; ReadRegKeyValue32W(HKEY__ *,ushort const *,ushort const *,uchar *,ulong *)
0x1800111a2  mov     ebx, eax
0x1800111a4  test    eax, eax
0x1800111a6  jz      short loc_1800111F1
0x1800111a8  cmp     eax, 2
0x1800111ab  jnz     short loc_1800111B7
0x1800111ad  xor     ebx, ebx
0x1800111af  lea     edi, [rbx+1]
0x1800111b2  jmp     loc_1800112B5
0x1800111b7  cmp     eax, edi
0x1800111b9  jz      short loc_1800111F1
0x1800111bb  test    eax, eax
0x1800111bd  jle     short loc_1800111C8
0x1800111bf  movzx   ebx, ax
0x1800111c2  or      ebx, 80070000h
0x1800111c8  mov     r9d, 79h ; 'y'; unsigned int
0x1800111ce  lea     rdx, aIsrestoreneede; "IsRestoreNeeded, ReadRegKeyValue32W(pws"...
0x1800111d5  mov     r8, r12; unsigned __int16 *
0x1800111d8  mov     ecx, ebx; int
0x1800111da  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x1800111df  lea     rax, aReadregkeyvalu; "ReadRegKeyValue32W(pwszMsdtcRestoreKey)"...
0x1800111e6  mov     r9d, 7Ah ; 'z'
0x1800111ec  jmp     loc_1800110B0
0x1800111f1  mov     ecx, dword ptr [rsp+78h+Size]; Size
0x1800111f8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800111fd  mov     rsi, rax
0x180011200  test    rax, rax
0x180011203  jnz     short loc_18001123E
0x180011205  mov     edi, 8007000Eh
0x18001120a  lea     rdx, aIsrestoreneede_4; "IsRestoreNeeded, new BYTE[cbSizeOfData]"...
0x180011211  mov     ecx, edi; int
0x180011213  mov     r9d, 83h; unsigned int
0x180011219  mov     r8, r12; unsigned __int16 *
0x18001121c  mov     ebx, edi
0x18001121e  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x180011223  lea     rax, aNewByteCbsizeo; "new BYTE[cbSizeOfData] failed"
0x18001122a  mov     r9d, 84h
0x180011230  mov     [rsp+78h+var_48], rax
0x180011235  mov     dword ptr [rsp+78h+var_50], edi
0x180011239  jmp     loc_1800110B9
0x18001123e  lea     rax, [rsp+78h+Size]
0x180011246  mov     r9, rsi; unsigned __int8 *
0x180011249  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\MSD"...
0x180011250  mov     [rsp+78h+var_58], rax; unsigned int *
0x180011255  call    ?ReadRegKeyValue32W@@YAJPEAUHKEY__@@PEBG1PEAEPEAK@Z; ReadRegKeyValue32W(HKEY__ *,ushort const *,ushort const *,uchar *,ulong *)
0x18001125a  mov     ebx, eax
0x18001125c  test    eax, eax
0x18001125e  jz      short loc_18001129F
0x180011260  cmp     eax, 2
0x180011263  jz      loc_1800111AD
0x180011269  test    eax, eax
0x18001126b  jle     short loc_180011276
0x18001126d  movzx   ebx, ax
0x180011270  or      ebx, 80070000h
0x180011276  mov     r9d, 96h; unsigned int
0x18001127c  lea     rdx, aIsrestoreneede_3; "IsRestoreNeeded, ReadRegKeyValue32W(pws"...
0x180011283  mov     r8, r12; unsigned __int16 *
0x180011286  mov     ecx, ebx; int
0x180011288  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x18001128d  lea     rax, aReadregkeyvalu_2; "ReadRegKeyValue32W(pwszMsdtcRestoreKey)"...
0x180011294  mov     r9d, 97h
0x18001129a  jmp     loc_1800110B0
0x18001129f  mov     rdx, rsi; lpString2
0x1800112a2  mov     rcx, rbp; lpString1
0x1800112a5  xor     ebx, ebx
0x1800112a7  call    cs:__imp_lstrcmpiW
0x1800112ad  xor     edi, edi
0x1800112af  test    eax, eax
0x1800112b1  setnz   dil
0x1800112b5  lea     r13, aIsrestoreneede_0; "IsRestoreNeeded"
0x1800112bc  mov     rcx, rbp; Block
0x1800112bf  mov     [r14], edi
0x1800112c2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800112c7  mov     rcx, rsi; Block
0x1800112ca  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800112cf  mov     dword ptr [rsp+78h+var_40], edi
0x1800112d3  lea     rax, aOutBrestorenee; "Out, bRestoreNeeded = %d"
0x1800112da  mov     [rsp+78h+var_48], rax
0x1800112df  mov     edx, 6
0x1800112e4  mov     dword ptr [rsp+78h+var_50], ebx
0x1800112e8  mov     r9d, 0B7h
0x1800112ee  mov     r8, r12
0x1800112f1  mov     [rsp+78h+var_58], r13
0x1800112f6  lea     ecx, [rdx+0Bh]
0x1800112f9  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800112fe  lea     r11, [rsp+78h+var_28]
0x180011303  mov     eax, ebx
0x180011305  mov     rbx, [r11+30h]
0x180011309  mov     rbp, [r11+38h]
0x18001130d  mov     rsp, r11
0x180011310  pop     r14
0x180011312  pop     r13
0x180011314  pop     r12
0x180011316  pop     rdi
0x180011317  pop     rsi
0x180011318  retn
```
