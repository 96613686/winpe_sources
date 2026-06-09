# PipHardwareConfigInit

- ea: `0x140c6879c`
- end: `0x140c68d25`
- name: `PipHardwareConfigInit`
- size: `1417`
- prototype: `__int64 __fastcall(GUID *Guid)`
- caller_count: `1`
- callee_count: `15`
- tags: `reparse_path, registry_config, installer_update`

## callers

- `0x140c669ac`

## callees

- `0x1404a46a8`
- `0x1406dc8c0`
- `0x1406dd5c0`
- `0x1406ddfe0`
- `0x1406defc0`
- `0x140760438`
- `0x1407605cc`
- `0x140833e58`
- `0x14087852c`
- `0x1408eeed8`
- `0x1409230b0`
- `0x140a95b68`
- `0x140bb19f0`
- `0x140c68668`
- `0x140c6879c`

## string_xrefs

- `0x140c687e4`: `\Registry\Machine\System\Setup`
- `0x140c688ad`: `LastConfig`

## pseudocode

```c
__int64 __fastcall PipHardwareConfigInit(GUID *Guid)
{
  HANDLE v2; // r15
  int v3; // eax
  void *v4; // rsi
  int CachedContextBaseKey; // ebx
  HANDLE v6; // r12
  int v7; // eax
  HANDLE v8; // rdi
  int RegistryValue; // r14d
  unsigned int v10; // eax
  unsigned int v11; // r14d
  bool v12; // zf
  __int64 v13; // rcx
  int v14; // r14d
  bool v15; // r14
  unsigned int Data; // [rsp+30h] [rbp-D0h] BYREF
  PVOID P; // [rsp+38h] [rbp-C8h]
  UNICODE_STRING v19; // [rsp+40h] [rbp-C0h] BYREF
  UNICODE_STRING ValueName; // [rsp+50h] [rbp-B0h] BYREF
  void *v21; // [rsp+60h] [rbp-A0h] BYREF
  int v22; // [rsp+68h] [rbp-98h] BYREF
  __int64 v23; // [rsp+70h] [rbp-90h] BYREF
  HANDLE v24; // [rsp+78h] [rbp-88h] BYREF
  HANDLE Handle; // [rsp+80h] [rbp-80h] BYREF
  HANDLE KeyHandle; // [rsp+88h] [rbp-78h] BYREF
  __int64 v27; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v28[528]; // [rsp+A0h] [rbp-60h] BYREF

  Data = -1;
  v23 = 0;
  v27 = 0;
  v22 = 0;
  v24 = 0;
  Handle = 0;
  KeyHandle = 0;
  v2 = 0;
  v21 = 0;
  P = 0;
  *(_QWORD *)&ValueName.Length = 4063292;
  v19 = 0;
  ValueName.Buffer = L"\\Registry\\Machine\\System\\Setup";
  v3 = IopCreateRegistryKeyEx(&v21, 0, &ValueName, 983103, 0, 0);
  v4 = v21;
  if ( v3 < 0 )
    v4 = 0;
  if ( v4 )
  {
    *(_DWORD *)&ValueName.Length = 1703960;
    ValueName.Buffer = L"Respecialize";
    ZwDeleteValueKey(v4, &ValueName);
  }
  CachedContextBaseKey = PnpCtxGetCachedContextBaseKey(*(_QWORD *)&PiPnpRtlCtx, 15, &KeyHandle);
  if ( CachedContextBaseKey >= 0 )
  {
    CachedContextBaseKey = RtlStringFromGUID(Guid, &PnpCurrentHardwareConfigurationGuidString);
    if ( CachedContextBaseKey >= 0 )
    {
      v6 = KeyHandle;
      v19.Buffer = L"LastConfig";
      *(_DWORD *)&v19.Length = 1441812;
      CachedContextBaseKey = ZwSetValueKey(
                               KeyHandle,
                               &v19,
                               0,
                               1u,
                               PnpCurrentHardwareConfigurationGuidString.Buffer,
                               PnpCurrentHardwareConfigurationGuidString.Length + 2);
      if ( CachedContextBaseKey >= 0 )
      {
        v7 = IopCreateRegistryKeyEx(&Handle, v6, &PnpCurrentHardwareConfigurationGuidString, 983103, 0, &v22);
        v8 = Handle;
        CachedContextBaseKey = v7;
        if ( v7 >= 0 )
        {
          RegistryValue = IopGetRegistryValue(Handle);
          CachedContextBaseKey = -1073741823;
          if ( RegistryValue >= 0 )
          {
            if ( *((_DWORD *)P + 1) == 4 && *((_DWORD *)P + 3) == 4 )
              Data = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
            else
              RegistryValue = -1073741823;
            ExFreePoolWithTag(P, 0);
            if ( RegistryValue >= 0 )
              goto LABEL_25;
          }
          Data = 0;
          if ( (int)IopGetRegistryValue(v6) >= 0 )
          {
            if ( *((_DWORD *)P + 1) == 4 && *((_DWORD *)P + 3) == 4 )
              Data = *(_DWORD *)((char *)P + *((unsigned int *)P + 2)) + 1;
            ExFreePoolWithTag(P, 0);
          }
          v10 = Data;
          v11 = Data - 1;
          if ( Data != Data - 1 )
          {
            do
            {
              v12 = (unsigned __int8)PipHardwareConfigExists(v6, v10) == 0;
              v10 = Data;
              if ( v12 )
                break;
              v10 = Data + 1;
              Data = v10;
            }
            while ( v10 != v11 );
            if ( v10 != v11 )
            {
              *(_DWORD *)&v19.Length = 917516;
              v19.Buffer = L"LastId";
              ZwSetValueKey(v6, &v19, 0, 4u, &Data, 4u);
              v19.Buffer = L"Id";
              *(_DWORD *)&v19.Length = 393220;
              CachedContextBaseKey = ZwSetValueKey(v8, &v19, 0, 4u, &Data, 4u);
              if ( CachedContextBaseKey >= 0 )
              {
LABEL_25:
                PnpCurrentHardwareConfigurationIndex = Data;
                KeQueryBootTimeValues(&Handle, &v23, &v27);
                v23 -= v27;
                v19.Buffer = L"LastUse";
                *(_DWORD *)&v19.Length = 1048590;
                ZwSetValueKey(v8, &v19, 0, 3u, &v23, 8u);
                v19.Buffer = (wchar_t *)L"Current";
                *(_DWORD *)&v19.Length = 1048590;
                CachedContextBaseKey = IopCreateRegistryKeyEx(&v24, v6, &v19, 983103, 3, 0);
                if ( CachedContextBaseKey < 0
                  || (LODWORD(v21) = 260,
                      CachedContextBaseKey = PnpCtxRegQueryKeyPathName(v13, v8, v28, &v21),
                      CachedContextBaseKey < 0) )
                {
                  v2 = v24;
                }
                else
                {
                  v2 = v24;
                  CachedContextBaseKey = ZwSetValueKey(v24, &CmSymbolicLinkValueName, 0, 6u, v28, 2 * (_DWORD)v21 - 2);
                  if ( CachedContextBaseKey >= 0 )
                  {
                    if ( (_DWORD)InitSafeBootMode
                      || (int)IopGetRegistryValue(v8) >= 0
                      && (*((_DWORD *)P + 1) != 4 || *((_DWORD *)P + 3) != 4
                        ? (v14 = 0)
                        : (v14 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2))),
                          ExFreePoolWithTag(P, 0),
                          v14) )
                    {
                      if ( (int)PipHardwareConfigClearStartOverrides(Data) >= 0 )
                      {
                        *(_DWORD *)&ValueName.Length = 786442;
                        ValueName.Buffer = L"Reset";
                        ZwDeleteValueKey(v8, &ValueName);
                      }
                    }
                    if ( v4 )
                    {
                      if ( v22 == 1 )
                        goto LABEL_49;
                      v15 = 0;
                      if ( (int)IopGetRegistryValue(v4) >= 0 )
                      {
                        if ( *((_DWORD *)P + 1) == 4 && *((_DWORD *)P + 3) == 4 )
                          v15 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2)) == 1;
                        ExFreePoolWithTag(P, 0);
                        if ( v15 )
                          goto LABEL_49;
                      }
                      if ( (int)IopGetRegistryValue(v8) >= 0 )
                      {
                        if ( *((_DWORD *)P + 1) == 4 && *((_DWORD *)P + 3) == 4 )
                          v15 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2)) == 1;
                        ExFreePoolWithTag(P, 0);
                        if ( v15 )
                        {
LABEL_49:
                          if ( (int)PipHardwareConfigTriggerRespecialize(v4) >= 0 )
                          {
                            *(_DWORD *)&ValueName.Length = 1703960;
                            ValueName.Buffer = L"Respecialize";
                            ZwDeleteValueKey(v8, &ValueName);
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
        if ( v8 )
          ZwClose(v8);
        if ( v2 )
          ZwClose(v2);
      }
    }
  }
  if ( v4 )
    ZwClose(v4);
  return (unsigned int)CachedContextBaseKey;
}

```

## disassembly

```asm
0x140c6879c  push    rbp
0x140c6879e  push    rbx
0x140c6879f  push    rsi
0x140c687a0  push    rdi
0x140c687a1  push    r12
0x140c687a3  push    r13
0x140c687a5  push    r14
0x140c687a7  push    r15
0x140c687a9  lea     rbp, [rsp-1C8h]
0x140c687b1  sub     rsp, 2C8h
0x140c687b8  mov     rax, cs:__security_cookie
0x140c687bf  xor     rax, rsp
0x140c687c2  mov     [rbp+200h+var_50], rax
0x140c687c9  xor     r13d, r13d
0x140c687cc  mov     [rsp+300h+var_2D0], 0FFFFFFFFh
0x140c687d4  mov     rdi, rcx
0x140c687d7  mov     qword ptr [rsp+300h+DataSize], r13
0x140c687dc  xorps   xmm0, xmm0
0x140c687df  mov     dword ptr [rsp+300h+Data], r13d
0x140c687e4  lea     rax, aRegistryMachin_222; "\\Registry\\Machine\\System\\Setup"
0x140c687eb  mov     [rsp+300h+var_290], r13
0x140c687f0  mov     r14d, 0F003Fh
0x140c687f6  mov     [rbp+200h+var_270], r13
0x140c687fa  mov     r9d, r14d
0x140c687fd  mov     [rsp+300h+var_298], r13d
0x140c68802  lea     r8, [rsp+300h+ValueName]
0x140c68807  mov     [rsp+300h+var_288], r13
0x140c6880c  xor     edx, edx
0x140c6880e  mov     [rbp+200h+Handle], r13
0x140c68812  lea     rcx, [rsp+300h+var_2A0]
0x140c68817  mov     [rbp+200h+KeyHandle], r13
0x140c6881b  mov     r15d, r13d
0x140c6881e  mov     [rsp+300h+var_2A0], r13
0x140c68823  mov     [rsp+300h+P], r13
0x140c68828  mov     qword ptr [rsp+300h+ValueName.Length], 3E003Ch
0x140c68831  movups  xmmword ptr [rsp+300h+var_2C0.Length], xmm0
0x140c68836  mov     [rsp+300h+ValueName.Buffer], rax
0x140c6883b  call    IopCreateRegistryKeyEx
0x140c68840  mov     rsi, [rsp+300h+var_2A0]
0x140c68845  test    eax, eax
0x140c68847  lea     rax, aRespecialize; "Respecialize"
0x140c6884e  cmovs   rsi, r13
0x140c68852  test    rsi, rsi
0x140c68855  jz      short loc_140C68871
0x140c68857  lea     rdx, [rsp+300h+ValueName]; ValueName
0x140c6885c  mov     dword ptr [rsp+300h+ValueName.Length], 1A0018h
0x140c68864  mov     rcx, rsi; KeyHandle
0x140c68867  mov     [rsp+300h+ValueName.Buffer], rax
0x140c6886c  call    ZwDeleteValueKey
0x140c68871  mov     rcx, cs:PiPnpRtlCtx
0x140c68878  lea     r8, [rbp+200h+KeyHandle]
0x140c6887c  mov     edx, 0Fh
0x140c68881  call    _PnpCtxGetCachedContextBaseKey
0x140c68886  mov     ebx, eax
0x140c68888  test    eax, eax
0x140c6888a  js      loc_140C68CF2
0x140c68890  lea     rdx, PnpCurrentHardwareConfigurationGuidString; GuidString
0x140c68897  mov     rcx, rdi; Guid
0x140c6889a  call    RtlStringFromGUID
0x140c6889f  mov     ebx, eax
0x140c688a1  test    eax, eax
0x140c688a3  js      loc_140C68CF2
0x140c688a9  mov     r12, [rbp+200h+KeyHandle]
0x140c688ad  lea     rax, aLastconfig; "LastConfig"
0x140c688b4  mov     [rsp+300h+var_2C0.Buffer], rax
0x140c688b9  lea     rdx, [rsp+300h+var_2C0]; ValueName
0x140c688be  movzx   eax, cs:PnpCurrentHardwareConfigurationGuidString.Length
0x140c688c5  mov     r9d, 1; Type
0x140c688cb  add     eax, 2
0x140c688ce  mov     dword ptr [rsp+300h+var_2C0.Length], 160014h
0x140c688d6  mov     [rsp+300h+DataSize], eax; DataSize
0x140c688da  xor     r8d, r8d; TitleIndex
0x140c688dd  mov     rax, cs:PnpCurrentHardwareConfigurationGuidString.Buffer
0x140c688e4  mov     rcx, r12; KeyHandle
0x140c688e7  mov     [rsp+300h+Data], rax; Data
0x140c688ec  call    ZwSetValueKey
0x140c688f1  mov     ebx, eax
0x140c688f3  test    eax, eax
0x140c688f5  js      loc_140C68CF2
0x140c688fb  lea     rax, [rsp+300h+var_298]
0x140c68900  mov     r9d, r14d
0x140c68903  mov     qword ptr [rsp+300h+DataSize], rax
0x140c68908  lea     r8, PnpCurrentHardwareConfigurationGuidString
0x140c6890f  mov     rdx, r12
0x140c68912  mov     dword ptr [rsp+300h+Data], r13d
0x140c68917  lea     rcx, [rbp+200h+Handle]
0x140c6891b  call    IopCreateRegistryKeyEx
0x140c68920  mov     rdi, [rbp+200h+Handle]
0x140c68924  mov     ebx, eax
0x140c68926  test    eax, eax
0x140c68928  js      loc_140C68CD8
0x140c6892e  lea     r9, [rsp+300h+P]
0x140c68933  xor     r8d, r8d
0x140c68936  lea     rdx, aId; "Id"
0x140c6893d  mov     rcx, rdi; KeyHandle
0x140c68940  call    IopGetRegistryValue
0x140c68945  mov     r14d, eax
0x140c68948  mov     ebx, 0C0000001h
0x140c6894d  mov     eax, 4
0x140c68952  test    r14d, r14d
0x140c68955  js      short loc_140C6898C
0x140c68957  mov     r8, [rsp+300h+P]
0x140c6895c  cmp     [r8+4], eax
0x140c68960  jnz     short loc_140C68976
0x140c68962  cmp     [r8+0Ch], eax
0x140c68966  jnz     short loc_140C68976
0x140c68968  mov     eax, [r8+8]
0x140c6896c  mov     ecx, [rax+r8]
0x140c68970  mov     [rsp+300h+var_2D0], ecx
0x140c68974  jmp     short loc_140C68979
0x140c68976  mov     r14d, ebx
0x140c68979  xor     edx, edx; Tag
0x140c6897b  mov     rcx, r8; P
0x140c6897e  call    ExFreePoolWithTag
0x140c68983  test    r14d, r14d
0x140c68986  jns     loc_140C68A83
0x140c6898c  lea     r9, [rsp+300h+P]
0x140c68991  mov     [rsp+300h+var_2D0], r13d
0x140c68996  xor     r8d, r8d
0x140c68999  lea     rdx, aLastid; "LastId"
0x140c689a0  mov     rcx, r12; KeyHandle
0x140c689a3  call    IopGetRegistryValue
0x140c689a8  test    eax, eax
0x140c689aa  js      short loc_140C689D3
0x140c689ac  mov     rcx, [rsp+300h+P]; P
0x140c689b1  mov     eax, 4
0x140c689b6  cmp     [rcx+4], eax
0x140c689b9  jnz     short loc_140C689CC
0x140c689bb  cmp     [rcx+0Ch], eax
0x140c689be  jnz     short loc_140C689CC
0x140c689c0  mov     eax, [rcx+8]
0x140c689c3  mov     edx, [rax+rcx]
0x140c689c6  inc     edx
0x140c689c8  mov     [rsp+300h+var_2D0], edx
0x140c689cc  xor     edx, edx; Tag
0x140c689ce  call    ExFreePoolWithTag
0x140c689d3  mov     eax, [rsp+300h+var_2D0]
0x140c689d7  lea     r14d, [rax-1]
0x140c689db  cmp     eax, r14d
0x140c689de  jz      loc_140C68CD8
0x140c689e4  mov     edx, eax
0x140c689e6  mov     rcx, r12
0x140c689e9  call    PipHardwareConfigExists
0x140c689ee  test    al, al
0x140c689f0  mov     eax, [rsp+300h+var_2D0]
0x140c689f4  jz      short loc_140C68A01
0x140c689f6  inc     eax
0x140c689f8  mov     [rsp+300h+var_2D0], eax
0x140c689fc  cmp     eax, r14d
0x140c689ff  jnz     short loc_140C689E4
0x140c68a01  cmp     eax, r14d
0x140c68a04  jz      loc_140C68CD8
0x140c68a0a  lea     rax, aLastid; "LastId"
0x140c68a11  mov     dword ptr [rsp+300h+var_2C0.Length], 0E000Ch
0x140c68a19  mov     [rsp+300h+var_2C0.Buffer], rax
0x140c68a1e  lea     rdx, [rsp+300h+var_2C0]; ValueName
0x140c68a23  mov     ebx, 4
0x140c68a28  lea     rax, [rsp+300h+var_2D0]
0x140c68a2d  mov     [rsp+300h+DataSize], ebx; DataSize
0x140c68a31  mov     r9d, ebx; Type
0x140c68a34  xor     r8d, r8d; TitleIndex
0x140c68a37  mov     [rsp+300h+Data], rax; Data
0x140c68a3c  mov     rcx, r12; KeyHandle
0x140c68a3f  call    ZwSetValueKey
0x140c68a44  lea     rax, aId; "Id"
0x140c68a4b  mov     [rsp+300h+DataSize], ebx; DataSize
0x140c68a4f  mov     [rsp+300h+var_2C0.Buffer], rax
0x140c68a54  lea     rdx, [rsp+300h+var_2C0]; ValueName
0x140c68a59  lea     rax, [rsp+300h+var_2D0]
0x140c68a5e  mov     dword ptr [rsp+300h+var_2C0.Length], 60004h
0x140c68a66  mov     r9d, ebx; Type
0x140c68a69  mov     [rsp+300h+Data], rax; Data
0x140c68a6e  xor     r8d, r8d; TitleIndex
0x140c68a71  mov     rcx, rdi; KeyHandle
0x140c68a74  call    ZwSetValueKey
0x140c68a79  mov     ebx, eax
0x140c68a7b  test    eax, eax
0x140c68a7d  js      loc_140C68CD8
0x140c68a83  mov     eax, [rsp+300h+var_2D0]
0x140c68a87  lea     r8, [rbp+200h+var_270]
0x140c68a8b  lea     rdx, [rsp+300h+var_290]
0x140c68a90  mov     cs:PnpCurrentHardwareConfigurationIndex, eax
0x140c68a96  lea     rcx, [rbp+200h+Handle]
0x140c68a9a  call    KeQueryBootTimeValues
0x140c68a9f  mov     rax, [rbp+200h+var_270]
0x140c68aa3  lea     rdx, [rsp+300h+var_2C0]; ValueName
0x140c68aa8  sub     [rsp+300h+var_290], rax
0x140c68aad  mov     ebx, 3
0x140c68ab2  lea     rax, aLastuse_0; "LastUse"
0x140c68ab9  mov     [rsp+300h+DataSize], 8; DataSize
0x140c68ac1  mov     [rsp+300h+var_2C0.Buffer], rax
0x140c68ac6  mov     r9d, ebx; Type
0x140c68ac9  lea     rax, [rsp+300h+var_290]
0x140c68ace  mov     dword ptr [rsp+300h+var_2C0.Length], 10000Eh
0x140c68ad6  xor     r8d, r8d; TitleIndex
0x140c68ad9  mov     [rsp+300h+Data], rax; Data
0x140c68ade  mov     rcx, rdi; KeyHandle
0x140c68ae1  call    ZwSetValueKey
0x140c68ae6  lea     rax, aCurrent_1; "Current"
0x140c68aed  mov     qword ptr [rsp+300h+DataSize], r13
0x140c68af2  mov     r9d, 0F003Fh
0x140c68af8  mov     [rsp+300h+var_2C0.Buffer], rax
0x140c68afd  lea     r8, [rsp+300h+var_2C0]
0x140c68b02  mov     dword ptr [rsp+300h+var_2C0.Length], 10000Eh
0x140c68b0a  mov     rdx, r12
0x140c68b0d  mov     dword ptr [rsp+300h+Data], ebx
0x140c68b11  lea     rcx, [rsp+300h+var_288]
0x140c68b16  call    IopCreateRegistryKeyEx
0x140c68b1b  mov     ebx, eax
0x140c68b1d  test    eax, eax
0x140c68b1f  js      loc_140C68CD3
0x140c68b25  lea     r9, [rsp+300h+var_2A0]
0x140c68b2a  mov     dword ptr [rsp+300h+var_2A0], 104h
0x140c68b32  lea     r8, [rbp+200h+var_260]
0x140c68b36  mov     rdx, rdi
0x140c68b39  call    _PnpCtxRegQueryKeyPathName
0x140c68b3e  mov     ebx, eax
0x140c68b40  test    eax, eax
0x140c68b42  js      loc_140C68CD3
0x140c68b48  mov     eax, dword ptr [rsp+300h+var_2A0]
0x140c68b4c  lea     rdx, CmSymbolicLinkValueName; ValueName
0x140c68b53  mov     r15, [rsp+300h+var_288]
0x140c68b58  mov     r9d, 6; Type
0x140c68b5e  xor     r8d, r8d; TitleIndex
0x140c68b61  mov     rcx, r15; KeyHandle
0x140c68b64  lea     eax, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x140c68b6b  mov     [rsp+300h+DataSize], eax; DataSize
0x140c68b6f  lea     rax, [rbp+200h+var_260]
0x140c68b73  mov     [rsp+300h+Data], rax; Data
0x140c68b78  call    ZwSetValueKey
0x140c68b7d  mov     ebx, eax
0x140c68b7f  test    eax, eax
0x140c68b81  js      loc_140C68CD8
0x140c68b87  cmp     cs:InitSafeBootMode, r13d
0x140c68b8e  lea     r12, aReset; "Reset"
0x140c68b95  jnz     short loc_140C68BDA
0x140c68b97  lea     r9, [rsp+300h+P]
0x140c68b9c  xor     r8d, r8d
0x140c68b9f  mov     rdx, r12
0x140c68ba2  mov     rcx, rdi; KeyHandle
0x140c68ba5  call    IopGetRegistryValue
0x140c68baa  test    eax, eax
0x140c68bac  js      short loc_140C68C01
0x140c68bae  mov     rcx, [rsp+300h+P]; P
0x140c68bb3  mov     eax, 4
0x140c68bb8  cmp     [rcx+4], eax
0x140c68bbb  jnz     short loc_140C68BCB
0x140c68bbd  cmp     [rcx+0Ch], eax
0x140c68bc0  jnz     short loc_140C68BCB
0x140c68bc2  mov     eax, [rcx+8]
0x140c68bc5  mov     r14d, [rax+rcx]
0x140c68bc9  jmp     short loc_140C68BCE
0x140c68bcb  mov     r14d, r13d
0x140c68bce  xor     edx, edx; Tag
0x140c68bd0  call    ExFreePoolWithTag
0x140c68bd5  test    r14d, r14d
0x140c68bd8  jz      short loc_140C68C01
0x140c68bda  mov     ecx, [rsp+300h+var_2D0]
0x140c68bde  call    PipHardwareConfigClearStartOverrides
0x140c68be3  test    eax, eax
0x140c68be5  js      short loc_140C68C01
0x140c68be7  lea     rdx, [rsp+300h+ValueName]; ValueName
0x140c68bec  mov     dword ptr [rsp+300h+ValueName.Length], 0C000Ah
0x140c68bf4  mov     rcx, rdi; KeyHandle
0x140c68bf7  mov     [rsp+300h+ValueName.Buffer], r12
0x140c68bfc  call    ZwDeleteValueKey
0x140c68c01  test    rsi, rsi
0x140c68c04  jz      loc_140C68CD8
0x140c68c0a  cmp     [rsp+300h+var_298], 1
0x140c68c0f  jz      loc_140C68CA4
0x140c68c15  lea     r9, [rsp+300h+P]
0x140c68c1a  xor     r8d, r8d
0x140c68c1d  lea     rdx, aRespecializest; "RespecializeStarted"
0x140c68c24  mov     rcx, rsi; KeyHandle
0x140c68c27  mov     r14b, r13b
0x140c68c2a  call    IopGetRegistryValue
0x140c68c2f  mov     r12d, 4
0x140c68c35  test    eax, eax
0x140c68c37  js      short loc_140C68C61
0x140c68c39  mov     rcx, [rsp+300h+P]; P
0x140c68c3e  cmp     [rcx+4], r12d
0x140c68c42  jnz     short loc_140C68C55
0x140c68c44  cmp     [rcx+0Ch], r12d
0x140c68c48  jnz     short loc_140C68C55
0x140c68c4a  mov     eax, [rcx+8]
0x140c68c4d  cmp     dword ptr [rax+rcx], 1
0x140c68c51  setz    r14b
0x140c68c55  xor     edx, edx; Tag
0x140c68c57  call    ExFreePoolWithTag
0x140c68c5c  test    r14b, r14b
0x140c68c5f  jnz     short loc_140C68CA4
0x140c68c61  lea     r9, [rsp+300h+P]
0x140c68c66  xor     r8d, r8d
0x140c68c69  lea     rdx, aRespecialize; "Respecialize"
0x140c68c70  mov     rcx, rdi; KeyHandle
0x140c68c73  call    IopGetRegistryValue
0x140c68c78  test    eax, eax
0x140c68c7a  js      short loc_140C68CD8
0x140c68c7c  mov     rcx, [rsp+300h+P]; P
0x140c68c81  cmp     [rcx+4], r12d
  ... truncated ...
```
