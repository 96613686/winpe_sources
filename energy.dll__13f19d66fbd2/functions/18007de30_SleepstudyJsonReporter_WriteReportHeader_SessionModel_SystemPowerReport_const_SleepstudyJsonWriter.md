# SleepstudyJsonReporter::WriteReportHeader(SessionModel::SystemPowerReport const &,SleepstudyJsonWriter &)

- ea: `0x18007de30`
- end: `0x18007dffb`
- name: `?WriteReportHeader@SleepstudyJsonReporter@@AEAAJAEBVSystemPowerReport@SessionModel@@AEAVSleepstudyJsonWriter@@@Z`
- size: `459`
- prototype: `int(SleepstudyJsonReporter *__hidden this, const struct SessionModel::SystemPowerReport *, struct SleepstudyJsonWriter *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18004a360`

## callees

- `0x1800256d0`
- `0x18002574c`
- `0x18004ca90`
- `0x18007911c`
- `0x18007b62c`
- `0x18007de30`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x18007ded7`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x18007ded7`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18007dea9`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18007dea9`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x18007dec1`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x18007dec1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18007de9b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18007de9b`
- `RPCRT4!UuidCreate` at `0x18007de89`
- `RPCRT4!UuidCreate` at `0x18007de89`

## pseudocode

```c
__int64 __fastcall SleepstudyJsonReporter::WriteReportHeader(
        SleepstudyJsonReporter *this,
        const struct SessionModel::SystemPowerReport *a2,
        struct SleepstudyJsonWriter *a3)
{
  unsigned int v5; // ebx
  SleepstudyJsonReporter *v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  int v10; // [rsp+28h] [rbp-E8h]
  int v11; // [rsp+38h] [rbp-D8h]
  int v12; // [rsp+48h] [rbp-C8h]
  int v13; // [rsp+58h] [rbp-B8h]
  int v14; // [rsp+68h] [rbp-A8h]
  int v15; // [rsp+78h] [rbp-98h]
  struct _FILETIME FileTime; // [rsp+90h] [rbp-80h] BYREF
  struct _FILETIME LocalFileTime; // [rsp+98h] [rbp-78h] BYREF
  __int64 v18; // [rsp+A0h] [rbp-70h] BYREF
  __int64 v19; // [rsp+A8h] [rbp-68h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+B0h] [rbp-60h] BYREF
  struct _SYSTEMTIME v21; // [rsp+C0h] [rbp-50h] BYREF
  struct _SYSTEMTIME v22; // [rsp+D0h] [rbp-40h] BYREF
  struct _SYSTEMTIME LocalTime; // [rsp+E0h] [rbp-30h] BYREF
  UUID Uuid; // [rsp+F0h] [rbp-20h] BYREF

  LocalFileTime = 0;
  FileTime = 0;
  Uuid = 0;
  v5 = 1627;
  v22 = 0;
  v21 = 0;
  SystemTime = 0;
  LocalTime = 0;
  if ( !UuidCreate(&Uuid) )
  {
    GetSystemTime(&SystemTime);
    if ( SystemTimeToFileTime(&SystemTime, &FileTime) )
    {
      if ( SystemTimeToTzSpecificLocalTime(0, &SystemTime, &LocalTime)
        && FileTimeToLocalFileTime(&FileTime, &LocalFileTime) )
      {
        v6 = (SleepstudyJsonReporter *)(*((_QWORD *)a2 + 3) - *((_QWORD *)a2 + 4));
        v18 = (*(_QWORD *)&LocalFileTime - *(_QWORD *)&FileTime) / 600000000LL;
        SleepstudyJsonReporter::FormatDateTime(v6, (unsigned __int64)v6 / 0xA, &v22, &v21);
        SleepstudyJsonWriter::StartObject(a3, L"ReportInformation");
        v19 = *((_QWORD *)a2 + 4) / 0x989680uLL / 0x3C / 0x3C / 0x18;
        SleepstudyJsonWriter::WriteKeyValues<unsigned short const (&)[11],_GUID &,unsigned short const (&)[15],unsigned __int64,unsigned short const (&)[10],__int64 &,unsigned short const (&)[9],_SYSTEMTIME &,unsigned short const (&)[14],_SYSTEMTIME &,unsigned short const (&)[16],_SYSTEMTIME &,unsigned short const (&)[21],_SYSTEMTIME &>(
          a3,
          v19,
          v7,
          v8,
          &Uuid,
          v10,
          (unsigned __int64 *)&v19,
          v11,
          &v18,
          v12,
          &SystemTime,
          v13,
          &LocalTime,
          v14,
          &v22,
          v15,
          &v21);
        SleepstudyJsonWriter::EndObject(a3);
        return 0;
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18007de30  mov     [rsp-18h+arg_0], rbx
0x18007de35  push    rbp
0x18007de36  push    rsi
0x18007de37  push    rdi
0x18007de38  mov     rbp, rsp
0x18007de3b  sub     rsp, 110h
0x18007de42  mov     rax, cs:__security_cookie
0x18007de49  xor     rax, rsp
0x18007de4c  mov     [rbp+var_10], rax
0x18007de50  xorps   xmm0, xmm0
0x18007de53  mov     qword ptr [rbp+LocalFileTime.dwLowDateTime], 0
0x18007de5b  xorps   xmm1, xmm1
0x18007de5e  mov     qword ptr [rbp+FileTime.dwLowDateTime], 0
0x18007de66  lea     rcx, [rbp+Uuid]; Uuid
0x18007de6a  mov     rsi, r8
0x18007de6d  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x18007de71  mov     rdi, rdx
0x18007de74  mov     ebx, 65Bh
0x18007de79  movups  xmmword ptr [rbp+var_40.wYear], xmm1
0x18007de7d  movups  xmmword ptr [rbp+var_50.wYear], xmm0
0x18007de81  movups  xmmword ptr [rbp+SystemTime.wYear], xmm1
0x18007de85  movups  xmmword ptr [rbp+LocalTime.wYear], xmm0
0x18007de89  call    cs:__imp_UuidCreate
0x18007de8f  test    eax, eax
0x18007de91  jnz     loc_18007DFDA
0x18007de97  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x18007de9b  call    cs:__imp_GetSystemTime
0x18007dea1  lea     rdx, [rbp+FileTime]; lpFileTime
0x18007dea5  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x18007dea9  call    cs:__imp_SystemTimeToFileTime
0x18007deaf  test    eax, eax
0x18007deb1  jz      loc_18007DFDA
0x18007deb7  lea     r8, [rbp+LocalTime]; lpLocalTime
0x18007debb  xor     ecx, ecx; lpTimeZoneInformation
0x18007debd  lea     rdx, [rbp+SystemTime]; lpUniversalTime
0x18007dec1  call    cs:__imp_SystemTimeToTzSpecificLocalTime
0x18007dec7  test    eax, eax
0x18007dec9  jz      loc_18007DFDA
0x18007decf  lea     rdx, [rbp+LocalFileTime]; lpLocalFileTime
0x18007ded3  lea     rcx, [rbp+FileTime]; lpFileTime
0x18007ded7  call    cs:__imp_FileTimeToLocalFileTime
0x18007dedd  test    eax, eax
0x18007dedf  jz      loc_18007DFDA
0x18007dee5  mov     rcx, qword ptr [rbp+LocalFileTime.dwLowDateTime]
0x18007dee9  lea     r9, [rbp+var_50]; struct _SYSTEMTIME *
0x18007deed  sub     rcx, qword ptr [rbp+FileTime.dwLowDateTime]
0x18007def1  lea     r8, [rbp+var_40]; struct _SYSTEMTIME *
0x18007def5  mov     rax, 1CA213D840BAF7D5h
0x18007deff  imul    rcx
0x18007df02  mov     rcx, [rdi+18h]
0x18007df06  sub     rcx, [rdi+20h]; this
0x18007df0a  sar     rdx, 1Ah
0x18007df0e  mov     rax, rdx
0x18007df11  shr     rax, 3Fh
0x18007df15  add     rdx, rax
0x18007df18  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18007df22  mov     [rbp+var_70], rdx
0x18007df26  mul     rcx
0x18007df29  shr     rdx, 3; unsigned __int64
0x18007df2d  call    ?FormatDateTime@SleepstudyJsonReporter@@AEAAX_KPEAU_SYSTEMTIME@@1@Z; SleepstudyJsonReporter::FormatDateTime(unsigned __int64,_SYSTEMTIME *,_SYSTEMTIME *)
0x18007df32  lea     rdx, aReportinformat_0; "ReportInformation"
0x18007df39  mov     rcx, rsi; this
0x18007df3c  call    ?StartObject@SleepstudyJsonWriter@@QEAAXPEBG@Z; SleepstudyJsonWriter::StartObject(ushort const *)
0x18007df41  mov     rcx, 8888888888888889h
0x18007df4b  mov     rax, 0D6BF94D5E57A42BDh
0x18007df55  mul     qword ptr [rdi+20h]
0x18007df59  mov     rax, rcx
0x18007df5c  shr     rdx, 17h
0x18007df60  mul     rdx
0x18007df63  mov     rax, rcx
0x18007df66  mov     rcx, rsi; this
0x18007df69  shr     rdx, 5
0x18007df6d  mul     rdx
0x18007df70  mov     rax, 0AAAAAAAAAAAAAAABh
0x18007df7a  shr     rdx, 5
0x18007df7e  mul     rdx
0x18007df81  lea     rax, [rbp+var_50]
0x18007df85  mov     [rsp+110h+var_90], rax; struct _SYSTEMTIME *
0x18007df8d  lea     rax, [rbp+var_40]
0x18007df91  mov     [rsp+110h+var_A0], rax; struct _SYSTEMTIME *
0x18007df96  lea     rax, [rbp+LocalTime]
0x18007df9a  mov     [rsp+110h+var_B0], rax; struct _SYSTEMTIME *
0x18007df9f  lea     rax, [rbp+SystemTime]
0x18007dfa3  mov     [rsp+110h+var_C0], rax; struct _SYSTEMTIME *
0x18007dfa8  lea     rax, [rbp+var_70]
0x18007dfac  mov     [rsp+110h+var_D0], rax; __int64
0x18007dfb1  lea     rax, [rbp+var_68]
0x18007dfb5  mov     [rsp+110h+var_E0], rax; __int64
0x18007dfba  lea     rax, [rbp+Uuid]
0x18007dfbe  shr     rdx, 4
0x18007dfc2  mov     [rsp+110h+var_F0], rax; struct _GUID *
0x18007dfc7  mov     [rbp+var_68], rdx
0x18007dfcb  call    ??$WriteKeyValues@AEAY0L@$$CBGAEAU_GUID@@AEAY0P@$$CBG_KAEAY09$$CBGAEA_JAEAY08$$CBGAEAU_SYSTEMTIME@@AEAY0O@$$CBGAEAU2@AEAY0BA@$$CBGAEAU2@AEAY0BF@$$CBGAEAU2@@SleepstudyJsonWriter@@QEAAXPEBG0AEAY0L@$$CBGAEAU_GUID@@AEAY0P@$$CBG$$QEA_KAEAY09$$CBGAEA_JAEAY08$$CBGAEAU_SYSTEMTIME@@AEAY0O@$$CBG8AEAY0BA@$$CBG8AEAY0BF@$$CBG8@Z; SleepstudyJsonWriter::WriteKeyValues<ushort const (&)[11],_GUID &,ushort const (&)[15],unsigned __int64,ushort const (&)[10],__int64 &,ushort const (&)[9],_SYSTEMTIME &,ushort const (&)[14],_SYSTEMTIME &,ushort const (&)[16],_SYSTEMTIME &,ushort const (&)[21],_SYSTEMTIME &>(ushort const *,ushort const *,ushort const (&)[11],_GUID &,ushort const (&)[15],unsigned __int64 &&,ushort const (&)[10],__int64 &,ushort const (&)[9],_SYSTEMTIME &,ushort const (&)[14],_SYSTEMTIME &,ushort const (&)[16],_SYSTEMTIME &,ushort const (&)[21],_SYSTEMTIME &)
0x18007dfd0  mov     rcx, rsi; this
0x18007dfd3  call    ?EndObject@SleepstudyJsonWriter@@QEAAXXZ; SleepstudyJsonWriter::EndObject(void)
0x18007dfd8  xor     ebx, ebx
0x18007dfda  mov     eax, ebx
0x18007dfdc  mov     rcx, [rbp+var_10]
0x18007dfe0  xor     rcx, rsp; StackCookie
0x18007dfe3  call    __security_check_cookie
0x18007dfe8  mov     rbx, [rsp+110h+arg_0]
0x18007dff0  add     rsp, 110h
0x18007dff7  pop     rdi
0x18007dff8  pop     rsi
0x18007dff9  pop     rbp
0x18007dffa  retn
```
