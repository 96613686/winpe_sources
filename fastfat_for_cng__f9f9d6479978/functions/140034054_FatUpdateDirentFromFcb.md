# FatUpdateDirentFromFcb

- ea: `0x140034054`
- end: `0x14003459e`
- name: `FatUpdateDirentFromFcb`
- size: `1354`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, char)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x140024bd4`
- `0x140037ab0`
- `0x14003dba0`

## callees

- `0x1400019b8`
- `0x1400319bc`
- `0x1400333d0`
- `0x140034054`
- `0x14003805c`
- `0x140044bac`
- `0x140049634`

## import_xrefs

- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14005d441`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14005d441`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x14003421f`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x14003421f`
- `ntoskrnl!FsRtlNotifyFullReportChange` at `0x1400344d0`
- `ntoskrnl!FsRtlNotifyFullReportChange` at `0x1400344d0`
- `ntoskrnl!ExLocalTimeToSystemTime` at `0x1400342ee`
- `ntoskrnl!ExLocalTimeToSystemTime` at `0x1400342ee`
- `ntoskrnl!ExSystemTimeToLocalTime` at `0x140034165`
- `ntoskrnl!ExSystemTimeToLocalTime` at `0x14003417e`
- `ntoskrnl!ExSystemTimeToLocalTime` at `0x140034165`
- `ntoskrnl!ExSystemTimeToLocalTime` at `0x14003417e`
- `ntoskrnl!CcUnpinData` at `0x140034531`
- `ntoskrnl!CcUnpinData` at `0x14005d46f`
- `ntoskrnl!CcUnpinData` at `0x140034531`
- `ntoskrnl!CcUnpinData` at `0x14005d46f`

## pseudocode

```c
__int64 __fastcall FatUpdateDirentFromFcb(__int64 a1, __int64 a2, __int64 a3, __int64 a4, char a5)
{
  __int64 result; // rax
  int v8; // ebx
  struct _LIST_ENTRY **v9; // r12
  char v10; // r15
  ULONG FilterMatch; // r14d
  char v12; // cl
  bool v13; // al
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // rcx
  bool v17; // dl
  int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // r8
  char v21; // [rsp+51h] [rbp-77h]
  bool v22; // [rsp+52h] [rbp-76h]
  char v23; // [rsp+53h] [rbp-75h]
  __int64 v24; // [rsp+58h] [rbp-70h] BYREF
  int v25; // [rsp+60h] [rbp-68h]
  int v26; // [rsp+64h] [rbp-64h] BYREF
  int v27; // [rsp+68h] [rbp-60h]
  PVOID Bcb; // [rsp+70h] [rbp-58h] BYREF
  union _LARGE_INTEGER SystemTime; // [rsp+78h] [rbp-50h] BYREF
  union _LARGE_INTEGER v30; // [rsp+80h] [rbp-48h] BYREF
  union _LARGE_INTEGER LocalTime; // [rsp+88h] [rbp-40h] BYREF
  __int64 v32; // [rsp+90h] [rbp-38h]
  _UNKNOWN *retaddr; // [rsp+C8h] [rbp+0h] BYREF

  result = (__int64)&retaddr;
  v24 = 0;
  Bcb = 0;
  v8 = 0;
  v26 = 0;
  SystemTime.QuadPart = 0;
  v30.QuadPart = 0;
  LocalTime.QuadPart = 0;
  if ( *(_DWORD *)(a3 + 196) == 1 )
  {
    result = 1284;
    if ( *(_WORD *)a3 != 1284 )
    {
      v9 = (struct _LIST_ENTRY **)(a3 + 184);
      v32 = a3 + 184;
      result = *(_QWORD *)(a3 + 184);
      if ( (*(_DWORD *)(result + 200) & 0x4000) == 0 )
      {
        v10 = 0;
        FilterMatch = 0;
        SystemTime.QuadPart = MEMORY[0xFFFFF78000000014];
        v27 = *(_DWORD *)(a2 + 80) & 0x1000;
        if ( (*(_DWORD *)(a2 + 80) & 0x1000) == 0 || (v12 = 1, (*(_DWORD *)(a4 + 4) & 0x10) != 0) )
          v12 = 0;
        v21 = v12;
        if ( *(_WORD *)a3 != 1282 || (v23 = 1, (*(_DWORD *)(a2 + 80) & 0x2000) == 0) )
          v23 = 0;
        if ( (byte_140017D4C & 1) != 0
          && (v12 || (*(_DWORD *)(a2 + 80) & 0x80000) != 0)
          && (*(_DWORD *)(a4 + 4) & 0x20) == 0 )
        {
          ExSystemTimeToLocalTime((PLARGE_INTEGER)(a3 + 264), &LocalTime);
          ExSystemTimeToLocalTime(&SystemTime, &v30);
          LocalTime.QuadPart /= FatOneDay;
          v30.QuadPart /= FatOneDay;
          v13 = LocalTime.LowPart != v30.LowPart;
        }
        else
        {
          v13 = 0;
        }
        v22 = v13;
        if ( v27 || v23 || v21 || v13 || a5 )
        {
          v14 = *(_QWORD *)(a3 + 176);
          if ( v14 )
            FsRtlCheckOplockEx((POPLOCK)(v14 + 88), *(PIRP *)(a1 + 40), 0x10u, 0, 0, 0);
          FatGetDirentFromFcbOrDcb(a1, a3, 0, (unsigned int)&v24, (__int64)&Bcb);
          LOBYTE(v16) = v21;
          if ( v21 || (v17 = v22) )
          {
            LOBYTE(v15) = 1;
            FatNtTimeToFatTime(v16, &SystemTime, v15, &v26, 0);
            v8 = v26;
            LOBYTE(v16) = v21;
            v17 = v22;
          }
          if ( v27 )
          {
            *(_BYTE *)(v24 + 11) |= 0x20u;
            *(_BYTE *)(a3 + 546) |= 0x20u;
            FilterMatch = 4;
            v25 = 4;
            v10 = 1;
          }
          if ( (_BYTE)v16 )
          {
            *(union _LARGE_INTEGER *)(a3 + 272) = SystemTime;
            *(_DWORD *)(v24 + 22) = v8;
            FilterMatch |= 0x10u;
            v25 = FilterMatch;
            v10 = 1;
          }
          if ( v17 )
          {
            *(_QWORD *)(a3 + 264) = FatOneDay * v30.QuadPart;
            ExLocalTimeToSystemTime((PLARGE_INTEGER)(a3 + 264), (PLARGE_INTEGER)(a3 + 264));
            *(_WORD *)(v24 + 18) = HIWORD(v26);
            FilterMatch |= 0x20u;
            v25 = FilterMatch;
            v10 = 1;
          }
          if ( v23 )
          {
            v18 = *(_DWORD *)(a3 + 32);
            if ( *(_DWORD *)(v24 + 28) != v18 )
            {
              *(_DWORD *)(v24 + 28) = v18;
              FilterMatch |= 8u;
              v25 = FilterMatch;
              v10 = 1;
            }
            if ( ((__int64)(*v9)[12].Blink & 0x400000) != 0 && (*(_DWORD *)(a3 + 192) & 0x8000) != 0 )
            {
              if ( *(_WORD *)a3 == 1282 )
                FatUpdateFileHeader(a1, a3, *(_DWORD *)(a3 + 132), *(unsigned int *)(v24 + 28));
              v19 = v24;
              *(_BYTE *)(a3 + 136) = ((*(_BYTE *)(v24 + 28) + 15) & 0xF0) - *(_BYTE *)(v24 + 28);
              *(_DWORD *)(v19 + 28) = (*(_DWORD *)(v19 + 28) + 15) & 0xFFFFFFF0;
              *(_DWORD *)(v24 + 28) += *(_DWORD *)(a3 + 132);
              *(_BYTE *)(v24 + 12) = *(_BYTE *)(v24 + 12) & 0x1B
                                   | (4 * (*(_BYTE *)(a3 + 136) & 1 | (4 * (*(_BYTE *)(a3 + 136) & 0xFE))));
              if ( (*(_DWORD *)(a3 + 192) & 0x60000) != 0 )
                *(_BYTE *)(v24 + 12) |= 1u;
              else
                *(_BYTE *)(v24 + 12) &= ~1u;
              if ( *(_DWORD *)(a3 + 132) == HIDWORD((*v9)[23].Flink) )
                *(_BYTE *)(v24 + 12) &= ~2u;
              else
                *(_BYTE *)(v24 + 12) |= 2u;
              FilterMatch |= 8u;
              v25 = FilterMatch;
              v10 = 1;
            }
          }
          if ( ((__int64)(*v9)[12].Blink & 0x400000) != 0 && a5 )
          {
            if ( (*(_DWORD *)(a3 + 192) & 0x60000) != 0 )
              *(_BYTE *)(v24 + 12) |= 1u;
            else
              *(_BYTE *)(v24 + 12) &= ~1u;
            FilterMatch |= 4u;
            v25 = FilterMatch;
            v10 = 1;
          }
          if ( !*(_QWORD *)(a3 + 536) )
            FatSetFullFileNameInFcb(a1);
          FsRtlNotifyFullReportChange(
            (PNOTIFY_SYNC)(*v9)[51].Flink,
            *v9 + 50,
            (PSTRING)(a3 + 528),
            *(_WORD *)(a3 + 528) - *(_WORD *)(a3 + 544),
            0,
            0,
            FilterMatch,
            3u,
            0);
          if ( v10 )
          {
            v20 = 0;
            if ( FilterMatch != 32 )
              v20 = (__int64)*v9;
            FatSetDirtyBcb(a1, Bcb, v20, 1);
          }
          if ( Bcb )
          {
            CcUnpinData(Bcb);
            Bcb = 0;
          }
        }
        result = (__int64)*v9;
        if ( ((__int64)(*v9)[12].Blink & 0x400000) != 0 && a5 && *(_WORD *)a3 == 1282 )
          return FatSetPfileExtensionOnDisk(a1, a3, (*(_DWORD *)(a3 + 192) & 0x20000) != 0);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140034054  mov     rax, rsp
0x140034057  mov     [rax+10h], rbx
0x14003405b  mov     [rax+20h], rsi
0x14003405f  mov     [rax+18h], r8
0x140034063  mov     [rax+8], rcx
0x140034067  push    rdi
0x140034068  push    r12
0x14003406a  push    r13
0x14003406c  push    r14
0x14003406e  push    r15
0x140034070  sub     rsp, 0A0h
0x140034077  mov     rsi, r8
0x14003407a  mov     r13, rcx
0x14003407d  xor     edi, edi
0x14003407f  mov     [rax-70h], rdi
0x140034083  mov     [rax-58h], rdi
0x140034087  mov     ebx, edi
0x140034089  mov     [rax-64h], ebx
0x14003408c  mov     [rax-50h], rdi
0x140034090  mov     [rax-48h], rdi
0x140034094  mov     [rax-40h], rdi
0x140034098  cmp     dword ptr [r8+0C4h], 1
0x1400340a0  jnz     loc_140034580
0x1400340a6  mov     eax, 504h
0x1400340ab  cmp     [r8], ax
0x1400340af  jz      loc_140034580
0x1400340b5  lea     r12, [r8+0B8h]
0x1400340bc  mov     [rsp+0C8h+var_38], r12
0x1400340c4  mov     rax, [r12]
0x1400340c8  mov     ecx, [rax+0C8h]
0x1400340ce  bt      ecx, 0Eh
0x1400340d2  jb      loc_140034580
0x1400340d8  mov     r15b, dil
0x1400340db  mov     r14d, edi
0x1400340de  mov     rax, 0FFFFF78000000014h
0x1400340e8  mov     rax, [rax]
0x1400340eb  mov     qword ptr [rsp+0C8h+SystemTime], rax
0x1400340f0  mov     eax, [rdx+50h]
0x1400340f3  mov     ecx, 1000h
0x1400340f8  and     eax, ecx
0x1400340fa  mov     [rsp+0C8h+var_60], eax
0x1400340fe  mov     eax, [rdx+50h]
0x140034101  test    ecx, eax
0x140034103  jz      short loc_14003410F
0x140034105  mov     eax, [r9+4]
0x140034109  test    al, 10h
0x14003410b  mov     cl, 1
0x14003410d  jz      short loc_140034112
0x14003410f  mov     cl, dil
0x140034112  mov     [rsp+0C8h+var_77], cl
0x140034116  mov     eax, 502h
0x14003411b  cmp     [r8], ax
0x14003411f  jnz     short loc_14003412F
0x140034121  mov     eax, [rdx+50h]
0x140034124  bt      eax, 0Dh
0x140034128  mov     [rsp+0C8h+var_75], 1
0x14003412d  jb      short loc_140034134
0x14003412f  mov     [rsp+0C8h+var_75], dil
0x140034134  test    cs:byte_140017D4C, 1
0x14003413b  jz      loc_1400341C7
0x140034141  test    cl, cl
0x140034143  jnz     short loc_14003414E
0x140034145  mov     eax, [rdx+50h]
0x140034148  bt      eax, 13h
0x14003414c  jnb     short loc_1400341C7
0x14003414e  mov     eax, [r9+4]
0x140034152  test    al, 20h
0x140034154  jnz     short loc_1400341C7
0x140034156  lea     rcx, [r8+108h]; SystemTime
0x14003415d  lea     rdx, [rsp+0C8h+LocalTime]; LocalTime
0x140034165  call    cs:__imp_ExSystemTimeToLocalTime
0x14003416c  nop     dword ptr [rax+rax+00h]
0x140034171  lea     rdx, [rsp+0C8h+var_48]; LocalTime
0x140034179  lea     rcx, [rsp+0C8h+SystemTime]; SystemTime
0x14003417e  call    cs:__imp_ExSystemTimeToLocalTime
0x140034185  nop     dword ptr [rax+rax+00h]
0x14003418a  mov     rax, qword ptr [rsp+0C8h+LocalTime]
0x140034192  cqo
0x140034194  idiv    cs:FatOneDay
0x14003419b  mov     r8, rax
0x14003419e  mov     qword ptr [rsp+0C8h+LocalTime], rax
0x1400341a6  mov     rax, qword ptr [rsp+0C8h+var_48]
0x1400341ae  cqo
0x1400341b0  idiv    cs:FatOneDay
0x1400341b7  mov     qword ptr [rsp+0C8h+var_48], rax
0x1400341bf  cmp     r8d, eax
0x1400341c2  setnz   al
0x1400341c5  jmp     short loc_1400341CA
0x1400341c7  mov     al, dil
0x1400341ca  mov     [rsp+0C8h+var_76], al
0x1400341ce  cmp     [rsp+0C8h+var_60], edi
0x1400341d2  jnz     short loc_1400341FA
0x1400341d4  cmp     [rsp+0C8h+var_75], dil
0x1400341d9  jnz     short loc_1400341FA
0x1400341db  cmp     [rsp+0C8h+var_77], dil
0x1400341e0  jnz     short loc_1400341FA
0x1400341e2  test    al, al
0x1400341e4  jnz     short loc_1400341FA
0x1400341e6  cmp     [rsp+0C8h+arg_20], dil
0x1400341ee  jnz     short loc_1400341FA
0x1400341f0  mov     ebx, 502h
0x1400341f5  jmp     loc_140034542
0x1400341fa  mov     rcx, [rsi+0B0h]
0x140034201  test    rcx, rcx
0x140034204  jz      short loc_14003422B
0x140034206  add     rcx, 58h ; 'X'; Oplock
0x14003420a  mov     [rsp+0C8h+PostIrpRoutine], rdi; PostIrpRoutine
0x14003420f  mov     [rsp+0C8h+CompletionRoutine], rdi; CompletionRoutine
0x140034214  xor     r9d, r9d; Context
0x140034217  lea     r8d, [r9+10h]; Flags
0x14003421b  mov     rdx, [r13+28h]; Irp
0x14003421f  call    cs:__imp_FsRtlCheckOplockEx
0x140034226  nop     dword ptr [rax+rax+00h]
0x14003422b  lea     rax, [rsp+0C8h+Bcb]
0x140034230  mov     [rsp+0C8h+CompletionRoutine], rax
0x140034235  lea     r9, [rsp+0C8h+var_70]
0x14003423a  xor     r8d, r8d
0x14003423d  mov     rdx, rsi
0x140034240  mov     rcx, r13
0x140034243  call    FatGetDirentFromFcbOrDcb
0x140034248  mov     cl, [rsp+0C8h+var_77]
0x14003424c  test    cl, cl
0x14003424e  jnz     short loc_140034258
0x140034250  mov     dl, [rsp+0C8h+var_76]
0x140034254  test    dl, dl
0x140034256  jz      short loc_14003427B
0x140034258  mov     [rsp+0C8h+CompletionRoutine], rdi
0x14003425d  lea     r9, [rsp+0C8h+var_64]
0x140034262  mov     r8b, 1
0x140034265  lea     rdx, [rsp+0C8h+SystemTime]
0x14003426a  call    FatNtTimeToFatTime
0x14003426f  mov     ebx, [rsp+0C8h+var_64]
0x140034273  mov     cl, [rsp+0C8h+var_77]
0x140034277  mov     dl, [rsp+0C8h+var_76]
0x14003427b  cmp     [rsp+0C8h+var_60], edi
0x14003427f  jz      short loc_1400342A4
0x140034281  mov     rax, [rsp+0C8h+var_70]
0x140034286  or      byte ptr [rax+0Bh], 20h
0x14003428a  or      byte ptr [rsi+222h], 20h
0x140034291  mov     r14d, 4
0x140034297  mov     [rsp+0C8h+var_68], r14d
0x14003429c  mov     r15b, 1
0x14003429f  mov     [rsp+0C8h+var_78], r15b
0x1400342a4  test    cl, cl
0x1400342a6  jz      short loc_1400342CD
0x1400342a8  mov     rax, qword ptr [rsp+0C8h+SystemTime]
0x1400342ad  mov     [rsi+110h], rax
0x1400342b4  mov     rax, [rsp+0C8h+var_70]
0x1400342b9  mov     [rax+16h], ebx
0x1400342bc  or      r14d, 10h
0x1400342c0  mov     [rsp+0C8h+var_68], r14d
0x1400342c5  mov     r15b, 1
0x1400342c8  mov     [rsp+0C8h+var_78], r15b
0x1400342cd  test    dl, dl
0x1400342cf  jz      short loc_140034319
0x1400342d1  lea     rcx, [rsi+108h]; LocalTime
0x1400342d8  mov     rdx, qword ptr [rsp+0C8h+var_48]
0x1400342e0  imul    rdx, cs:FatOneDay
0x1400342e8  mov     [rcx], rdx
0x1400342eb  mov     rdx, rcx; SystemTime
0x1400342ee  call    cs:__imp_ExLocalTimeToSystemTime
0x1400342f5  nop     dword ptr [rax+rax+00h]
0x1400342fa  movzx   eax, word ptr [rsp+0C8h+var_64+2]
0x1400342ff  mov     rcx, [rsp+0C8h+var_70]
0x140034304  mov     [rcx+12h], ax
0x140034308  or      r14d, 20h
0x14003430c  mov     [rsp+0C8h+var_68], r14d
0x140034311  mov     r15b, 1
0x140034314  mov     [rsp+0C8h+var_78], r15b
0x140034319  cmp     [rsp+0C8h+var_75], dil
0x14003431e  jz      loc_140034430
0x140034324  mov     eax, [rsi+20h]
0x140034327  mov     rcx, [rsp+0C8h+var_70]
0x14003432c  cmp     [rcx+1Ch], eax
0x14003432f  jz      short loc_140034345
0x140034331  mov     [rcx+1Ch], eax
0x140034334  or      r14d, 8
0x140034338  mov     [rsp+0C8h+var_68], r14d
0x14003433d  mov     r15b, 1
0x140034340  mov     [rsp+0C8h+var_78], r15b
0x140034345  mov     rax, [r12]
0x140034349  mov     ecx, [rax+0C8h]
0x14003434f  mov     ebx, 502h
0x140034354  bt      ecx, 16h
0x140034358  jnb     loc_140034435
0x14003435e  test    dword ptr [rsi+0C0h], 8000h
0x140034368  jz      loc_140034435
0x14003436e  cmp     [rsi], bx
0x140034371  jnz     short loc_14003438E
0x140034373  mov     rax, [rsp+0C8h+var_70]
0x140034378  mov     r9d, [rax+1Ch]
0x14003437c  mov     r8d, [rsi+84h]
0x140034383  mov     rdx, rsi
0x140034386  mov     rcx, r13
0x140034389  call    FatUpdateFileHeader
0x14003438e  mov     rdx, [rsp+0C8h+var_70]
0x140034393  mov     cl, [rdx+1Ch]
0x140034396  lea     eax, [rcx+0Fh]
0x140034399  and     al, 0F0h
0x14003439b  sub     al, cl
0x14003439d  mov     [rsi+88h], al
0x1400343a3  mov     eax, [rdx+1Ch]
0x1400343a6  add     eax, 0Fh
0x1400343a9  and     eax, 0FFFFFFF0h
0x1400343ac  mov     [rdx+1Ch], eax
0x1400343af  mov     rcx, [rsp+0C8h+var_70]
0x1400343b4  mov     eax, [rsi+84h]
0x1400343ba  add     [rcx+1Ch], eax
0x1400343bd  mov     al, [rsi+88h]
0x1400343c3  mov     rdx, [rsp+0C8h+var_70]
0x1400343c8  mov     cl, al
0x1400343ca  and     cl, 0FEh
0x1400343cd  shl     cl, 2
0x1400343d0  and     al, 1
0x1400343d2  or      cl, al
0x1400343d4  shl     cl, 2
0x1400343d7  mov     al, [rdx+0Ch]
0x1400343da  and     al, 1Bh
0x1400343dc  or      cl, al
0x1400343de  mov     [rdx+0Ch], cl
0x1400343e1  mov     rax, [rsp+0C8h+var_70]
0x1400343e6  test    dword ptr [rsi+0C0h], 60000h
0x1400343f0  jz      short loc_1400343F8
0x1400343f2  or      byte ptr [rax+0Ch], 1
0x1400343f6  jmp     short loc_1400343FC
0x1400343f8  and     byte ptr [rax+0Ch], 0FEh
0x1400343fc  mov     rax, [r12]
0x140034400  mov     ecx, [rax+174h]
0x140034406  mov     rax, [rsp+0C8h+var_70]
0x14003440b  cmp     [rsi+84h], ecx
0x140034411  jz      short loc_140034419
0x140034413  or      byte ptr [rax+0Ch], 2
0x140034417  jmp     short loc_14003441D
0x140034419  and     byte ptr [rax+0Ch], 0FDh
0x14003441d  or      r14d, 8
0x140034421  mov     [rsp+0C8h+var_68], r14d
0x140034426  mov     r15b, 1
0x140034429  mov     [rsp+0C8h+var_78], r15b
0x14003442e  jmp     short loc_140034435
0x140034430  mov     ebx, 502h
0x140034435  mov     rax, [r12]
0x140034439  mov     ecx, [rax+0C8h]
0x14003443f  bt      ecx, 16h
0x140034443  jnb     short loc_14003447B
0x140034445  cmp     [rsp+0C8h+arg_20], dil
0x14003444d  jz      short loc_14003447B
0x14003444f  mov     rax, [rsp+0C8h+var_70]
0x140034454  test    dword ptr [rsi+0C0h], 60000h
0x14003445e  jz      short loc_140034466
0x140034460  or      byte ptr [rax+0Ch], 1
0x140034464  jmp     short loc_14003446A
0x140034466  and     byte ptr [rax+0Ch], 0FEh
0x14003446a  or      r14d, 4
0x14003446e  mov     [rsp+0C8h+var_68], r14d
0x140034473  mov     r15b, 1
0x140034476  mov     [rsp+0C8h+var_78], r15b
0x14003447b  cmp     [rsi+218h], rdi
0x140034482  jnz     short loc_14003448F
0x140034484  mov     rdx, rsi
0x140034487  mov     rcx, r13; int
0x14003448a  call    FatSetFullFileNameInFcb
0x14003448f  lea     r8, [rsi+210h]; FullTargetName
0x140034496  mov     rcx, [r12]
0x14003449a  movzx   r9d, word ptr [r8]
0x14003449e  sub     r9w, [rsi+220h]; TargetNameOffset
0x1400344a6  lea     rdx, [rcx+320h]; NotifyList
0x1400344ad  mov     [rsp+0C8h+TargetContext], rdi; TargetContext
0x1400344b2  mov     [rsp+0C8h+Action], 3; Action
0x1400344ba  mov     [rsp+0C8h+FilterMatch], r14d; FilterMatch
0x1400344bf  mov     [rsp+0C8h+PostIrpRoutine], rdi; NormalizedParentName
0x1400344c4  mov     [rsp+0C8h+CompletionRoutine], rdi; StreamName
0x1400344c9  mov     rcx, [rcx+330h]; NotifySync
0x1400344d0  call    cs:__imp_FsRtlNotifyFullReportChange
0x1400344d7  nop     dword ptr [rax+rax+00h]
0x1400344dc  test    r15b, r15b
0x1400344df  jz      short loc_1400344FE
0x1400344e1  cmp     r14d, 20h ; ' '
0x1400344e5  mov     r8, rdi
0x1400344e8  jz      short loc_1400344EE
0x1400344ea  mov     r8, [r12]
0x1400344ee  mov     r9b, 1
0x1400344f1  mov     rdx, [rsp+0C8h+Bcb]
0x1400344f6  mov     rcx, r13
0x1400344f9  call    FatSetDirtyBcb
0x1400344fe  jmp     short loc_140034527
0x140034500  mov     r13, [rsp+0C8h+arg_0]
0x140034508  mov     dword ptr [r13+48h], 0
0x140034510  xor     edi, edi
0x140034512  mov     ebx, 502h
0x140034517  mov     rsi, [rsp+0C8h+arg_10]
0x14003451f  mov     r12, [rsp+0C8h+var_38]
0x140034527  mov     rcx, [rsp+0C8h+Bcb]; Bcb
0x14003452c  test    rcx, rcx
0x14003452f  jz      short loc_140034542
0x140034531  call    cs:__imp_CcUnpinData
0x140034538  nop     dword ptr [rax+rax+00h]
0x14003453d  mov     [rsp+0C8h+Bcb], rdi
0x140034542  mov     rax, [r12]
0x140034546  mov     ecx, [rax+0C8h]
0x14003454c  bt      ecx, 16h
  ... truncated ...
```
