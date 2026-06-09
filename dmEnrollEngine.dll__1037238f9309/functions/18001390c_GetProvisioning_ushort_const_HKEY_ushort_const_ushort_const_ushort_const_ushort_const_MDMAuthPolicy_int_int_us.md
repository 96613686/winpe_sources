# GetProvisioning(ushort const *,HKEY__ *,ushort const *,ushort const *,ushort const *,ushort const *,MDMAuthPolicy,int,int,ushort const *,ushort * *,ulong,ulong,ulong,ushort const *,ushort const *,ushort const *,ulong,ushort const *,ulong *,ushort * *,ushort * *,ushort * const,ushort * *)

- ea: `0x18001390c`
- end: `0x180013b85`
- name: `?GetProvisioning@@YAJPEBGPEAUHKEY__@@0000W4MDMAuthPolicy@@HH0PEAPEAGKKK000K0PEAK33QEAG3@Z`
- size: `633`
- prototype: `__int64 __fastcall(__int64, __int64, const unsigned __int16 *, __int64, __int64, __int64, int, int, int, __int64, __int64, int, int, int, __int64, __int64, __int64, int, __int64, __int64, __int64, __int64, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180012e60`

## callees

- `0x18000dd20`
- `0x18001390c`
- `0x1800140d0`
- `0x180014148`
- `0x1800206a8`
- `0x180032f20`
- `0x18004b92c`
- `0x18004d194`
- `0x180051a58`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013a6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013ae2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013b14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013a6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013ae2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013b14`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180013a61`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180013ad8`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180013a61`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180013ad8`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180013b0a`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180013b0a`

## string_xrefs

- `0x180013b28`: `MachineEnrollmentProv.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall GetProvisioning(
        __int64 a1,
        __int64 a2,
        const unsigned __int16 *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int a7,
        int a8,
        int a9,
        __int64 a10,
        __int64 a11,
        int a12,
        int a13,
        int a14,
        __int64 a15,
        __int64 a16,
        __int64 a17,
        int a18,
        __int64 a19,
        __int64 a20,
        __int64 a21,
        __int64 a22,
        unsigned __int16 *a23,
        unsigned __int16 **a24)
{
  unsigned __int16 *v25; // rbx
  int ProvisioningPayload; // eax
  unsigned int v27; // eax
  __int64 cchWideChar; // rdi
  signed int LastError; // eax
  WCHAR *lpWideCharStr; // rax
  signed int v31; // eax
  unsigned __int16 *v32; // rdi
  int v33; // eax
  unsigned int v34; // ebx
  unsigned int v36; // [rsp+C8h] [rbp-19h] BYREF
  unsigned int v37; // [rsp+CCh] [rbp-15h] BYREF
  LPCCH lpMultiByteStr; // [rsp+D0h] [rbp-11h]
  _QWORD v39[2]; // [rsp+D8h] [rbp-9h] BYREF
  int v40; // [rsp+110h] [rbp+2Fh] BYREF

  v40 = 0;
  v25 = 0;
  lpMultiByteStr = 0;
  v37 = 0;
  v36 = 0;
  v39[0] = "GetProvisioning";
  v39[1] = &v40;
  ProvisioningPayload = RetrieveProvisioningPayload(
                          a1,
                          a2,
                          a3,
                          a4,
                          a5,
                          a6,
                          a7,
                          a8,
                          a9,
                          a10,
                          a11,
                          a12,
                          a13,
                          a14,
                          a18,
                          a19,
                          a20,
                          a21,
                          a22,
                          a15);
  v40 = ProvisioningPayload;
  if ( ProvisioningPayload == -2145910766 && a24 )
  {
    v37 = 0;
    ParseServiceURL(a3, &v37, a24, 0, 1);
    ProvisioningPayload = v40;
  }
  if ( ProvisioningPayload >= 0 )
  {
    v27 = MultiByteToWideChar(0xFDE9u, 0, lpMultiByteStr, -1, 0, 0);
    cchWideChar = v27;
    if ( v27 )
      goto LABEL_9;
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v40 = LastError;
    if ( LastError >= 0 )
    {
LABEL_9:
      v40 = ULongLongToULong(2 * cchWideChar, &v36);
      if ( v40 >= 0 )
      {
        lpWideCharStr = (WCHAR *)SafeHeapAlloc(v36);
        v25 = lpWideCharStr;
        if ( lpWideCharStr )
        {
          if ( MultiByteToWideChar(0xFDE9u, 0, lpMultiByteStr, -1, lpWideCharStr, cchWideChar) )
            goto LABEL_16;
          v31 = GetLastError();
          if ( v31 > 0 )
            v31 = (unsigned __int16)v31 | 0x80070000;
          v40 = v31;
          if ( v31 >= 0 )
          {
LABEL_16:
            v32 = a23;
            if ( (unsigned int)GetTempPath2W(260, a23) )
            {
              v40 = StringCchCatW(v32, 0x104u, L"MachineEnrollmentProv.xml");
              if ( v40 < 0 )
                goto LABEL_22;
              v33 = CMachineEnroller::WriteXmlToFile(v25, v32);
            }
            else
            {
              v33 = GetLastError();
              if ( v33 > 0 )
                v33 = (unsigned __int16)v33 | 0x80070000;
            }
            v40 = v33;
          }
        }
        else
        {
          v40 = -2147024882;
        }
      }
    }
  }
LABEL_22:
  SafeHeapFree((void *)lpMultiByteStr);
  SafeHeapFree(v25);
  v34 = v40;
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v39);
  return v34;
}

```

## disassembly

```asm
0x18001390c  mov     r11, rsp
0x18001390f  mov     [r11+8], rbx
0x180013913  mov     [r11+10h], rdi
0x180013917  push    rbp
0x180013918  lea     rbp, [r11-0Fh]
0x18001391c  sub     rsp, 0E0h
0x180013923  mov     rdi, r8
0x180013926  mov     [rbp+7+arg_18], 0
0x18001392d  xor     ebx, ebx
0x18001392f  mov     [rbp+7+lpMultiByteStr], rbx
0x180013933  mov     [rbp+7+var_1C], ebx
0x180013936  mov     [rbp+7+var_20], ebx
0x180013939  lea     rax, aGetprovisionin; "GetProvisioning"
0x180013940  mov     [rbp+7+var_10], rax
0x180013944  lea     rax, [rbp+7+arg_18]
0x180013948  mov     [rbp+7+var_8], rax
0x18001394c  lea     rax, [rbp+7+var_1C]
0x180013950  mov     [r11-30h], rax
0x180013954  lea     rax, [rbp+7+lpMultiByteStr]
0x180013958  mov     [r11-38h], rax
0x18001395c  mov     rax, [rbp+7+arg_80]
0x180013963  mov     [r11-40h], rax
0x180013967  mov     rax, [rbp+7+arg_78]
0x18001396e  mov     [r11-48h], rax
0x180013972  mov     rax, [rbp+7+arg_70]
0x180013979  mov     [r11-50h], rax
0x18001397d  mov     rax, [rbp+7+arg_A8]
0x180013984  mov     [r11-58h], rax
0x180013988  mov     rax, [rbp+7+arg_A0]
0x18001398f  mov     [r11-60h], rax
0x180013993  mov     rax, [rbp+7+arg_98]
0x18001399a  mov     [r11-68h], rax
0x18001399e  mov     rax, [rbp+7+arg_90]
0x1800139a5  mov     [r11-70h], rax
0x1800139a9  mov     eax, [rbp+7+arg_88]
0x1800139af  mov     [rsp+0E0h+var_70], eax
0x1800139b3  mov     eax, [rbp+7+arg_68]
0x1800139b6  mov     [rsp+0E0h+var_78], eax
0x1800139ba  mov     eax, [rbp+7+arg_60]
0x1800139bd  mov     [rsp+0E0h+var_80], eax
0x1800139c1  mov     eax, [rbp+7+arg_58]
0x1800139c4  mov     [rsp+0E0h+var_88], eax
0x1800139c8  mov     rax, [rbp+7+arg_50]
0x1800139cc  mov     qword ptr [rsp+0E0h+var_90], rax
0x1800139d1  mov     rax, [rbp+7+arg_48]
0x1800139d5  mov     [rsp+0E0h+var_98], rax
0x1800139da  mov     eax, [rbp+7+arg_40]
0x1800139dd  mov     dword ptr [rsp+0E0h+var_A0], eax
0x1800139e1  mov     eax, [rbp+7+arg_38]
0x1800139e4  mov     [rsp+0E0h+var_A8], eax
0x1800139e8  mov     eax, [rbp+7+arg_30]
0x1800139eb  mov     [rsp+0E0h+var_B0], eax
0x1800139ef  mov     rax, [rbp+7+arg_28]
0x1800139f3  mov     qword ptr [rsp+0E0h+cchWideChar], rax
0x1800139f8  mov     rax, [rbp+7+arg_20]
0x1800139fc  mov     [rsp+0E0h+lpWideCharStr], rax
0x180013a01  call    ?RetrieveProvisioningPayload@@YAJPEBGPEAUHKEY__@@0000W4MDMAuthPolicy@@HH0PEAPEAGKKKK0PEAK33000PEAPEAE4@Z; RetrieveProvisioningPayload(ushort const *,HKEY__ *,ushort const *,ushort const *,ushort const *,ushort const *,MDMAuthPolicy,int,int,ushort const *,ushort * *,ulong,ulong,ulong,ulong,ushort const *,ulong *,ushort * *,ushort * *,ushort const *,ushort const *,ushort const *,uchar * *,ulong *)
0x180013a06  mov     [rbp+7+arg_18], eax
0x180013a09  cmp     eax, 80180012h
0x180013a0e  jnz     short loc_180013A39
0x180013a10  mov     r8, [rbp+7+arg_B8]; unsigned __int16 **
0x180013a17  test    r8, r8
0x180013a1a  jz      short loc_180013A39
0x180013a1c  mov     [rbp+7+var_1C], ebx
0x180013a1f  mov     dword ptr [rsp+0E0h+lpWideCharStr], 1; int
0x180013a27  xor     r9d, r9d; unsigned __int16 **
0x180013a2a  lea     rdx, [rbp+7+var_1C]; unsigned int *
0x180013a2e  mov     rcx, rdi; unsigned __int16 *
0x180013a31  call    ?ParseServiceURL@@YAJPEBGPEAKPEAPEAG2H@Z; ParseServiceURL(ushort const *,ulong *,ushort * *,ushort * *,int)
0x180013a36  mov     eax, [rbp+7+arg_18]
0x180013a39  test    eax, eax
0x180013a3b  js      loc_180013B51
0x180013a41  mov     [rsp+0E0h+cchWideChar], 0; cchWideChar
0x180013a49  mov     [rsp+0E0h+lpWideCharStr], 0; lpWideCharStr
0x180013a52  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180013a56  mov     r8, [rbp+7+lpMultiByteStr]; lpMultiByteStr
0x180013a5a  xor     edx, edx; dwFlags
0x180013a5c  mov     ecx, 0FDE9h; CodePage
0x180013a61  call    cs:__imp_MultiByteToWideChar
0x180013a67  mov     edi, eax
0x180013a69  test    eax, eax
0x180013a6b  jnz     short loc_180013A8A
0x180013a6d  call    cs:__imp_GetLastError
0x180013a73  test    eax, eax
0x180013a75  jle     short loc_180013A7F
0x180013a77  movzx   eax, ax
0x180013a7a  or      eax, 80070000h
0x180013a7f  mov     [rbp+7+arg_18], eax
0x180013a82  test    eax, eax
0x180013a84  js      loc_180013B51
0x180013a8a  mov     rcx, rdi
0x180013a8d  add     rcx, rcx; unsigned __int64
0x180013a90  lea     rdx, [rbp+7+var_20]; unsigned int *
0x180013a94  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180013a99  mov     [rbp+7+arg_18], eax
0x180013a9c  test    eax, eax
0x180013a9e  js      loc_180013B51
0x180013aa4  mov     ecx, [rbp+7+var_20]; unsigned __int64
0x180013aa7  call    ?SafeHeapAlloc@@YAPEAX_K@Z; SafeHeapAlloc(unsigned __int64)
0x180013aac  mov     rbx, rax
0x180013aaf  test    rax, rax
0x180013ab2  jnz     short loc_180013AC0
0x180013ab4  mov     [rbp+7+arg_18], 8007000Eh
0x180013abb  jmp     loc_180013B51
0x180013ac0  mov     [rsp+0E0h+cchWideChar], edi; cchWideChar
0x180013ac4  mov     [rsp+0E0h+lpWideCharStr], rbx; lpWideCharStr
0x180013ac9  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180013acd  mov     r8, [rbp+7+lpMultiByteStr]; lpMultiByteStr
0x180013ad1  xor     edx, edx; dwFlags
0x180013ad3  mov     ecx, 0FDE9h; CodePage
0x180013ad8  call    cs:__imp_MultiByteToWideChar
0x180013ade  test    eax, eax
0x180013ae0  jnz     short loc_180013AFB
0x180013ae2  call    cs:__imp_GetLastError
0x180013ae8  test    eax, eax
0x180013aea  jle     short loc_180013AF4
0x180013aec  movzx   eax, ax
0x180013aef  or      eax, 80070000h
0x180013af4  mov     [rbp+7+arg_18], eax
0x180013af7  test    eax, eax
0x180013af9  js      short loc_180013B51
0x180013afb  mov     rdi, [rbp+7+arg_B0]
0x180013b02  mov     rdx, rdi
0x180013b05  mov     ecx, 104h
0x180013b0a  call    cs:__imp_GetTempPath2W
0x180013b10  test    eax, eax
0x180013b12  jnz     short loc_180013B28
0x180013b14  call    cs:__imp_GetLastError
0x180013b1a  test    eax, eax
0x180013b1c  jle     short loc_180013B4E
0x180013b1e  movzx   eax, ax
0x180013b21  or      eax, 80070000h
0x180013b26  jmp     short loc_180013B4E
0x180013b28  lea     r8, aMachineenrollm; "MachineEnrollmentProv.xml"
0x180013b2f  mov     edx, 104h; unsigned __int64
0x180013b34  mov     rcx, rdi; unsigned __int16 *
0x180013b37  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180013b3c  mov     [rbp+7+arg_18], eax
0x180013b3f  test    eax, eax
0x180013b41  js      short loc_180013B51
0x180013b43  mov     rdx, rdi; unsigned __int16 *
0x180013b46  mov     rcx, rbx; unsigned __int16 *
0x180013b49  call    ?WriteXmlToFile@CMachineEnroller@@SAJPEBG0@Z; CMachineEnroller::WriteXmlToFile(ushort const *,ushort const *)
0x180013b4e  mov     [rbp+7+arg_18], eax
0x180013b51  mov     rcx, [rbp+7+lpMultiByteStr]; void *
0x180013b55  call    ?SafeHeapFree@@YAHPEAX@Z; SafeHeapFree(void *)
0x180013b5a  mov     rcx, rbx; void *
0x180013b5d  call    ?SafeHeapFree@@YAHPEAX@Z; SafeHeapFree(void *)
0x180013b62  mov     ebx, [rbp+7+arg_18]
0x180013b65  lea     rcx, [rbp+7+var_10]; this
0x180013b69  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x180013b6e  mov     eax, ebx
0x180013b70  lea     r11, [rsp+0E0h+var_s0]
0x180013b78  mov     rbx, [r11+10h]
0x180013b7c  mov     rdi, [r11+18h]
0x180013b80  mov     rsp, r11
0x180013b83  pop     rbp
0x180013b84  retn
```
