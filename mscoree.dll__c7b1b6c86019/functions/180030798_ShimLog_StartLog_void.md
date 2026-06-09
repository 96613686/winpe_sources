# ShimLog::StartLog(void)

- ea: `0x180030798`
- end: `0x1800309cf`
- name: `?StartLog@ShimLog@@QEAAXXZ`
- size: `567`
- prototype: `void __fastcall(ShimLog *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180009af4`

## callees

- `0x180003070`
- `0x180003ed0`
- `0x180007300`
- `0x18000a59c`
- `0x18000b324`
- `0x180030578`
- `0x180030758`
- `0x180030798`
- `0x180041ac0`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x1800308bf`
- `KERNEL32!GetModuleFileNameW` at `0x1800308bf`
- `KERNEL32!CreateFileW` at `0x180030828`
- `KERNEL32!CreateFileW` at `0x180030828`
- `KERNEL32!WriteFile` at `0x180030865`
- `KERNEL32!WriteFile` at `0x180030865`
- `KERNEL32!GetLocalTime` at `0x1800308f9`
- `KERNEL32!GetLocalTime` at `0x1800308f9`
- `KERNEL32!GetTimeFormatW` at `0x180030922`
- `KERNEL32!GetTimeFormatW` at `0x180030922`
- `KERNEL32!GetDateFormatW` at `0x18003094d`
- `KERNEL32!GetDateFormatW` at `0x18003094d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ShimLog::StartLog(LPCWSTR *this)
{
  unsigned __int16 *ConfigString; // rdx
  WCHAR *FileW; // rax
  WCHAR *v4; // rdx
  LPWSTR v5; // r8
  int TimeFormatW; // edi
  int DateFormatW; // eax
  __int16 Buffer[2]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+44h] [rbp-BCh] BYREF
  unsigned __int16 *v10; // [rsp+48h] [rbp-B8h] BYREF
  BOOL v11; // [rsp+50h] [rbp-B0h]
  _SYSTEMTIME SystemTime; // [rsp+58h] [rbp-A8h] BYREF
  LPWSTR lpFilename[2]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v14; // [rsp+80h] [rbp-80h]
  _BYTE v15[520]; // [rsp+88h] [rbp-78h] BYREF
  WCHAR DateStr[104]; // [rsp+290h] [rbp+190h] BYREF
  WCHAR TimeStr[104]; // [rsp+360h] [rbp+260h] BYREF

  ConfigString = (unsigned __int16 *)GetConfigString(L"CLRLoadLogDir", 1, 0);
  v10 = ConfigString;
  v11 = ConfigString != 0;
  if ( ConfigString )
  {
    if ( ShimLog::FindLogFileName((ShimLog *)this, ConfigString) )
    {
      FileW = (WCHAR *)CreateFileW(*this, 0x40000000u, 0, 0, 1u, 0x80u, 0);
      this[2] = FileW;
      if ( FileW != (WCHAR *)-1LL )
      {
        Buffer[0] = -257;
        NumberOfBytesWritten = 0;
        WriteFile(FileW, Buffer, 2u, &NumberOfBytesWritten, 0);
        if ( NumberOfBytesWritten == 2 )
        {
          *((_DWORD *)this + 2) = 1;
          lpFilename[0] = 0;
          lpFilename[1] = 0;
          v14 = 512;
          if ( (int)CQuickArrayBase<unsigned short>::ReSizeNoThrow(lpFilename, 269) >= 0 )
          {
            v4 = (WCHAR *)v15;
            if ( lpFilename[0] )
              v4 = lpFilename[0];
            if ( GetModuleFileNameW(0, v4, v14 >> 1) )
            {
              v5 = (LPWSTR)v15;
              if ( lpFilename[0] )
                v5 = lpFilename[0];
              ShimLog::Log((ShimLog *)this, 0x4Du, v5);
              ShimLog::LogNewline((ShimLog *)this);
            }
          }
          SystemTime = 0;
          GetLocalTime(&SystemTime);
          TimeFormatW = GetTimeFormatW(0x400u, 0, &SystemTime, 0, TimeStr, 100);
          DateFormatW = GetDateFormatW(0x400u, 0, &SystemTime, 0, DateStr, 100);
          if ( TimeFormatW > 0
            && (unsigned int)TimeFormatW < 0x64
            && DateFormatW > 0
            && (unsigned int)DateFormatW < 0x64 )
          {
            ShimLog::Log((ShimLog *)this, 0x4Cu, TimeStr, DateStr);
          }
          ShimLog::Log((ShimLog *)this, 0x46u);
          ShimLog::LogNewline((ShimLog *)this);
          CQuickArray<unsigned short>::~CQuickArray<unsigned short>(lpFilename);
        }
      }
    }
  }
  Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(&v10);
}

```

## disassembly

```asm
0x180030798  mov     [rsp-8+arg_8], rbx
0x18003079d  mov     [rsp-8+arg_10], rdi
0x1800307a2  push    rbp
0x1800307a3  lea     rbp, [rsp-340h]
0x1800307ab  sub     rsp, 440h
0x1800307b2  mov     rax, cs:__security_cookie
0x1800307b9  xor     rax, rsp
0x1800307bc  mov     [rbp+340h+var_10], rax
0x1800307c3  mov     rbx, rcx
0x1800307c6  xor     r8d, r8d
0x1800307c9  lea     edi, [r8+1]
0x1800307cd  mov     edx, edi
0x1800307cf  lea     rcx, aClrloadlogdir; "CLRLoadLogDir"
0x1800307d6  call    ?GetConfigString@@YAPEAGPEBGHW4VERSION_ARCHITECTURE@@@Z; GetConfigString(ushort const *,int,VERSION_ARCHITECTURE)
0x1800307db  mov     rdx, rax; unsigned __int16 *
0x1800307de  mov     [rsp+440h+var_3F8], rax
0x1800307e3  xor     eax, eax
0x1800307e5  test    rdx, rdx
0x1800307e8  cmovnz  eax, edi
0x1800307eb  mov     [rsp+440h+var_3F0], eax
0x1800307ef  jz      loc_1800309A1
0x1800307f5  mov     rcx, rbx; this
0x1800307f8  call    ?FindLogFileName@ShimLog@@AEAAHPEAG@Z; ShimLog::FindLogFileName(ushort *)
0x1800307fd  test    eax, eax
0x1800307ff  jz      loc_1800309A1
0x180030805  mov     [rsp+440h+hTemplateFile], 0; hTemplateFile
0x18003080e  mov     [rsp+440h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180030816  mov     [rsp+440h+dwCreationDisposition], edi; dwCreationDisposition
0x18003081a  xor     r9d, r9d; lpSecurityAttributes
0x18003081d  xor     r8d, r8d; dwShareMode
0x180030820  mov     edx, 40000000h; dwDesiredAccess
0x180030825  mov     rcx, [rbx]; lpFileName
0x180030828  call    cs:__imp_CreateFileW
0x18003082e  mov     [rbx+10h], rax
0x180030832  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180030836  jz      loc_1800309A1
0x18003083c  mov     [rsp+440h+Buffer], 0FEFFh
0x180030843  mov     [rsp+440h+NumberOfBytesWritten], 0
0x18003084b  mov     qword ptr [rsp+440h+dwCreationDisposition], 0; lpOverlapped
0x180030854  lea     r9, [rsp+440h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180030859  lea     r8d, [rdi+1]; nNumberOfBytesToWrite
0x18003085d  lea     rdx, [rsp+440h+Buffer]; lpBuffer
0x180030862  mov     rcx, rax; hFile
0x180030865  call    cs:__imp_WriteFile
0x18003086b  cmp     [rsp+440h+NumberOfBytesWritten], 2
0x180030870  jnz     loc_1800309A1
0x180030876  mov     [rbx+8], edi
0x180030879  mov     [rsp+440h+lpFilename], 0
0x180030882  mov     [rsp+440h+var_3C8], 0
0x18003088b  mov     [rbp+340h+var_3C0], 200h
0x180030893  mov     edx, 10Dh
0x180030898  lea     rcx, [rsp+440h+lpFilename]
0x18003089d  call    ?ReSizeNoThrow@?$CQuickArrayBase@G@@QEAAJ_K@Z; CQuickArrayBase<ushort>::ReSizeNoThrow(unsigned __int64)
0x1800308a2  test    eax, eax
0x1800308a4  js      short loc_1800308EC
0x1800308a6  mov     r8, [rbp+340h+var_3C0]
0x1800308aa  shr     r8, 1; nSize
0x1800308ad  lea     rdx, [rbp+340h+var_3B8]
0x1800308b1  mov     rax, [rsp+440h+lpFilename]
0x1800308b6  test    rax, rax
0x1800308b9  cmovnz  rdx, rax; lpFilename
0x1800308bd  xor     ecx, ecx; hModule
0x1800308bf  call    cs:__imp_GetModuleFileNameW
0x1800308c5  test    eax, eax
0x1800308c7  jz      short loc_1800308EC
0x1800308c9  lea     r8, [rbp+340h+var_3B8]
0x1800308cd  mov     rax, [rsp+440h+lpFilename]
0x1800308d2  test    rax, rax
0x1800308d5  cmovnz  r8, rax
0x1800308d9  lea     edx, [rdi+4Ch]; unsigned int
0x1800308dc  mov     rcx, rbx; this
0x1800308df  call    ?Log@ShimLog@@QEAAXIZZ; ShimLog::Log(uint,...)
0x1800308e4  mov     rcx, rbx; this
0x1800308e7  call    ?LogNewline@ShimLog@@QEAAXXZ; ShimLog::LogNewline(void)
0x1800308ec  xorps   xmm0, xmm0
0x1800308ef  movups  xmmword ptr [rsp+440h+SystemTime.wYear], xmm0
0x1800308f4  lea     rcx, [rsp+440h+SystemTime]; lpSystemTime
0x1800308f9  call    cs:__imp_GetLocalTime
0x1800308ff  mov     [rsp+440h+dwFlagsAndAttributes], 64h ; 'd'; cchTime
0x180030907  lea     rax, [rbp+340h+TimeStr]
0x18003090e  mov     qword ptr [rsp+440h+dwCreationDisposition], rax; lpTimeStr
0x180030913  xor     r9d, r9d; lpFormat
0x180030916  lea     r8, [rsp+440h+SystemTime]; lpTime
0x18003091b  xor     edx, edx; dwFlags
0x18003091d  mov     ecx, 400h; Locale
0x180030922  call    cs:__imp_GetTimeFormatW
0x180030928  mov     edi, eax
0x18003092a  mov     [rsp+440h+dwFlagsAndAttributes], 64h ; 'd'; cchDate
0x180030932  lea     rax, [rbp+340h+DateStr]
0x180030939  mov     qword ptr [rsp+440h+dwCreationDisposition], rax; lpDateStr
0x18003093e  xor     r9d, r9d; lpFormat
0x180030941  lea     r8, [rsp+440h+SystemTime]; lpDate
0x180030946  xor     edx, edx; dwFlags
0x180030948  mov     ecx, 400h; Locale
0x18003094d  call    cs:__imp_GetDateFormatW
0x180030953  test    edi, edi
0x180030955  jle     short loc_180030980
0x180030957  cmp     edi, 64h ; 'd'
0x18003095a  jnb     short loc_180030980
0x18003095c  test    eax, eax
0x18003095e  jle     short loc_180030980
0x180030960  cmp     eax, 64h ; 'd'
0x180030963  jnb     short loc_180030980
0x180030965  lea     r9, [rbp+340h+DateStr]
0x18003096c  lea     r8, [rbp+340h+TimeStr]
0x180030973  mov     edx, 4Ch ; 'L'; unsigned int
0x180030978  mov     rcx, rbx; this
0x18003097b  call    ?Log@ShimLog@@QEAAXIZZ; ShimLog::Log(uint,...)
0x180030980  mov     edx, 46h ; 'F'; unsigned int
0x180030985  mov     rcx, rbx; this
0x180030988  call    ?Log@ShimLog@@QEAAXIZZ; ShimLog::Log(uint,...)
0x18003098d  mov     rcx, rbx; this
0x180030990  call    ?LogNewline@ShimLog@@QEAAXXZ; ShimLog::LogNewline(void)
0x180030995  nop
0x180030996  lea     rcx, [rsp+440h+lpFilename]
0x18003099b  call    ??1?$CQuickArray@G@@QEAA@XZ; CQuickArray<ushort>::~CQuickArray<ushort>(void)
0x1800309a0  nop
0x1800309a1  lea     rcx, [rsp+440h+var_3F8]
0x1800309a6  call    ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
0x1800309ab  mov     rcx, [rbp+340h+var_10]
0x1800309b2  xor     rcx, rsp; StackCookie
0x1800309b5  call    __security_check_cookie
0x1800309ba  lea     r11, [rsp+440h+var_s0]
0x1800309c2  mov     rbx, [r11+18h]
0x1800309c6  mov     rdi, [r11+20h]
0x1800309ca  mov     rsp, r11
0x1800309cd  pop     rbp
0x1800309ce  retn
```
