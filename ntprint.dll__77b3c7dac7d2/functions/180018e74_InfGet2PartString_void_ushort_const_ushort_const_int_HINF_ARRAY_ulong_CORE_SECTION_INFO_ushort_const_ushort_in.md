# InfGet2PartString(void *,ushort const *,ushort const *,int,_HINF_ARRAY *,ulong,_CORE_SECTION_INFO *,ushort const *,ushort * *,int *)

- ea: `0x180018e74`
- end: `0x18001914d`
- name: `?InfGet2PartString@@YAXPEAXPEBG1HPEAU_HINF_ARRAY@@KPEAU_CORE_SECTION_INFO@@1PEAPEAGPEAH@Z`
- size: `729`
- prototype: `void __usercall(HINF InfHandle@<rcx>, PCWSTR Section@<rdx>, PCWSTR@<r8>, int@<r9d>, struct _HINF_ARRAY *, unsigned int, struct _CORE_SECTION_INFO *, PCWSTR Key, unsigned __int16 **, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800217e0`

## callees

- `0x180007944`
- `0x18000d57c`
- `0x18000d624`
- `0x1800162c8`
- `0x180018d3c`
- `0x180018e74`
- `0x18001f094`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180018fc2`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180018fc2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001911e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001911e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018f4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800190ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800190fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018f4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800190ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800190fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001907a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800190a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800190d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800190e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800190f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001907a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800190a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800190d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800190e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800190f1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001905b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001905b`
- `SETUPAPI!SetupFindFirstLineW` at `0x180018ee5`
- `SETUPAPI!SetupFindFirstLineW` at `0x180018f01`
- `SETUPAPI!SetupFindFirstLineW` at `0x180018ee5`
- `SETUPAPI!SetupFindFirstLineW` at `0x180018f01`

## string_xrefs

- `0x180018fdd`: `Must strip the extra space after the comma.`

## pseudocode

```c
void __fastcall InfGet2PartString(
        HINF InfHandle,
        PCWSTR Section,
        PCWSTR a3,
        int a4,
        struct _HINF_ARRAY *a5,
        unsigned int a6,
        struct _CORE_SECTION_INFO *a7,
        PCWSTR Key,
        unsigned __int16 **a9,
        int *hMem)
{
  DWORD LastError; // eax
  wchar_t *v15; // rax
  DWORD v16; // eax
  DWORD v17; // eax
  struct _INFCONTEXT Context; // [rsp+38h] [rbp-20h] BYREF

  memset(&Context, 0, sizeof(Context));
  if ( !*hMem )
  {
    ClassInstallerTelemetry::WriteDbgTraceInfo(
      "InfGet2PartString",
      L"Searching for value of field %ws under %ws",
      Key,
      Section);
    if ( SetupFindFirstLineW(InfHandle, Section, Key, &Context)
      || a4 && SetupFindFirstLineW(InfHandle, a3, Key, &Context)
      || a6 && (unsigned int)InfFindLineFromCoreSections(Key, a5, a6, a7, &Context, hMem) )
    {
      if ( *hMem )
      {
        LastError = GetLastError();
        ClassInstallerTelemetry::WriteDbgTraceWarning(
          "InfGet2PartString",
          L"Error finding value of field %ws: %d",
          Key,
          LastError);
      }
      else
      {
        InfGetString(&Context, 1u, (__int64)hMem);
        if ( *hMem || !*a9 )
        {
          ClassInstallerTelemetry::WriteDbgTraceInfo("InfGet2PartString", L"Field %ws has no value.", Key);
        }
        else
        {
          ClassInstallerTelemetry::WriteDbgTraceInfo("InfGet2PartString", L"Field %ws has value %ws", Key);
          v15 = wcschr(*a9, 0x2Cu);
          if ( v15 )
          {
            *v15 = 0;
          }
          else
          {
            ClassInstallerTelemetry::WriteDbgTraceInfo(
              "InfGet2PartString",
              L"Must strip the extra space after the comma.");
            InfGetString(&Context, 2u, (__int64)hMem);
            if ( *a9 )
            {
              LocalFree(*a9);
              *a9 = 0;
            }
            *hMem = 1;
            v17 = GetLastError();
            ClassInstallerTelemetry::WriteDbgTraceError("InfGet2PartString", L"Error getting value: %d", v17);
            SetLastError(0x800300FD);
          }
        }
      }
    }
    else
    {
      *a9 = 0;
      v16 = GetLastError();
      ClassInstallerTelemetry::WriteDbgTraceWarning("InfGet2PartString", L"Error getting value: %d", v16);
    }
  }
}

```

## disassembly

```asm
0x180018e74  push    rbp
0x180018e76  push    rbx
0x180018e77  push    rsi
0x180018e78  push    rdi
0x180018e79  push    r12
0x180018e7b  push    r13
0x180018e7d  push    r14
0x180018e7f  push    r15
0x180018e81  mov     rbp, rsp
0x180018e84  sub     rsp, 58h
0x180018e88  mov     rsi, [rbp+hMem]
0x180018e8f  xor     eax, eax
0x180018e91  xor     r13d, r13d
0x180018e94  mov     qword ptr [rbp+Context.Section], rax
0x180018e98  xorps   xmm0, xmm0
0x180018e9b  mov     [rbp+var_28], r13d
0x180018e9f  mov     r14d, r9d
0x180018ea2  mov     r12, r8
0x180018ea5  mov     r15, rdx
0x180018ea8  mov     rbx, rcx
0x180018eab  movups  xmmword ptr [rbp+Context.Inf], xmm0
0x180018eaf  cmp     [rsi], r13d
0x180018eb2  jnz     loc_18001913C
0x180018eb8  mov     rdi, [rbp+Key]
0x180018ebf  lea     rcx, aInfget2partstr_1; "InfGet2PartString"
0x180018ec6  mov     r9, rdx
0x180018ec9  mov     r8, rdi
0x180018ecc  lea     rdx, aSearchingForVa; "Searching for value of field %ws under "...
0x180018ed3  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180018ed8  lea     r9, [rbp+Context]; Context
0x180018edc  mov     r8, rdi; Key
0x180018edf  mov     rdx, r15; Section
0x180018ee2  mov     rcx, rbx; InfHandle
0x180018ee5  call    cs:__imp_SetupFindFirstLineW
0x180018eeb  test    eax, eax
0x180018eed  jnz     short loc_180018F45
0x180018eef  test    r14d, r14d
0x180018ef2  jz      short loc_180018F0B
0x180018ef4  lea     r9, [rbp+Context]; Context
0x180018ef8  mov     r8, rdi; Key
0x180018efb  mov     rdx, r12; Section
0x180018efe  mov     rcx, rbx; InfHandle
0x180018f01  call    cs:__imp_SetupFindFirstLineW
0x180018f07  test    eax, eax
0x180018f09  jnz     short loc_180018F45
0x180018f0b  mov     r8d, [rbp+arg_28]; unsigned int
0x180018f0f  test    r8d, r8d
0x180018f12  jz      short loc_180018F36
0x180018f14  mov     r9, [rbp+arg_30]; struct _CORE_SECTION_INFO *
0x180018f18  lea     rax, [rbp+Context]
0x180018f1c  mov     rdx, [rbp+arg_20]; struct _HINF_ARRAY *
0x180018f20  mov     rcx, rdi; Key
0x180018f23  mov     [rsp+58h+var_30], rsi; int *
0x180018f28  mov     [rsp+58h+var_38], rax; struct _INFCONTEXT *
0x180018f2d  call    ?InfFindLineFromCoreSections@@YAHPEBGPEAU_HINF_ARRAY@@KPEAU_CORE_SECTION_INFO@@PEAU_INFCONTEXT@@PEAH@Z; InfFindLineFromCoreSections(ushort const *,_HINF_ARRAY *,ulong,_CORE_SECTION_INFO *,_INFCONTEXT *,int *)
0x180018f32  test    eax, eax
0x180018f34  jnz     short loc_180018F45
0x180018f36  mov     rax, [rbp+arg_40]
0x180018f3d  mov     [rax], r13
0x180018f40  jmp     loc_1800190AC
0x180018f45  cmp     [rsi], r13d
0x180018f48  jz      short loc_180018F6E
0x180018f4a  call    cs:__imp_GetLastError
0x180018f50  mov     r8, rdi
0x180018f53  lea     rdx, aErrorFindingVa; "Error finding value of field %ws: %d"
0x180018f5a  mov     r9d, eax
0x180018f5d  lea     rcx, aInfget2partstr_1; "InfGet2PartString"
0x180018f64  call    ?WriteDbgTraceWarning@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180018f69  jmp     loc_18001913C
0x180018f6e  mov     rbx, [rbp+arg_40]
0x180018f75  lea     r9, [rbp+var_28]
0x180018f79  mov     r8, rbx
0x180018f7c  mov     [rsp+58h+var_38], rsi; __int64
0x180018f81  mov     edx, 1; FieldIndex
0x180018f86  lea     rcx, [rbp+Context]; Context
0x180018f8a  call    InfGetString
0x180018f8f  cmp     [rsi], r13d
0x180018f92  jnz     loc_180019126
0x180018f98  mov     r9, [rbx]
0x180018f9b  test    r9, r9
0x180018f9e  jz      loc_180019126
0x180018fa4  mov     r8, rdi
0x180018fa7  lea     rdx, aFieldWsHasValu; "Field %ws has value %ws"
0x180018fae  lea     rcx, aInfget2partstr_1; "InfGet2PartString"
0x180018fb5  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180018fba  mov     rcx, [rbx]; Str
0x180018fbd  mov     edx, 2Ch ; ','; Ch
0x180018fc2  call    cs:__imp_wcschr
0x180018fc8  mov     [rbp+hMem], rax
0x180018fcf  test    rax, rax
0x180018fd2  jz      short loc_180018FDD
0x180018fd4  mov     [rax], r13w
0x180018fd8  jmp     loc_18001913C
0x180018fdd  lea     rdx, aMustStripTheEx; "Must strip the extra space after the co"...
0x180018fe4  mov     rdi, r13
0x180018fe7  lea     rcx, aInfget2partstr_1; "InfGet2PartString"
0x180018fee  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180018ff3  lea     r9, [rbp+var_28]
0x180018ff7  mov     [rsp+58h+var_38], rsi; __int64
0x180018ffc  lea     r8, [rbp+hMem]
0x180019003  mov     edx, 2; FieldIndex
0x180019008  lea     rcx, [rbp+Context]; Context
0x18001900c  call    InfGetString
0x180019011  mov     r15, [rbp+hMem]
0x180019018  cmp     [rsi], r13d
0x18001901b  jnz     loc_1800190CA
0x180019021  test    r15, r15
0x180019024  jz      loc_1800190CA
0x18001902a  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001902e  mov     rax, r14
0x180019031  inc     rax
0x180019034  cmp     [r15+rax*2], r13w
0x180019039  jnz     short loc_180019031
0x18001903b  mov     rdx, [rbx]
0x18001903e  mov     rcx, r14
0x180019041  inc     rcx
0x180019044  cmp     [rdx+rcx*2], r13w
0x180019049  jnz     short loc_180019041
0x18001904b  lea     r12d, [rax+2]
0x18001904f  add     r12d, ecx
0x180019052  mov     ecx, 40h ; '@'; uFlags
0x180019057  lea     edx, [r12+r12]; uBytes
0x18001905b  call    cs:__imp_LocalAlloc
0x180019061  mov     rdi, rax
0x180019064  test    rax, rax
0x180019067  jz      short loc_1800190CA
0x180019069  mov     r8, [rbx]; unsigned __int16 *
0x18001906c  mov     rcx, rax; unsigned __int16 *
0x18001906f  mov     edx, r12d; unsigned __int64
0x180019072  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180019077  mov     rcx, [rbx]; hMem
0x18001907a  call    cs:__imp_LocalFree
0x180019080  mov     [rbx], rdi
0x180019083  inc     r14
0x180019086  cmp     [rdi+r14*2], r13w
0x18001908b  jnz     short loc_180019083
0x18001908d  lea     eax, [r14+1]
0x180019091  mov     r8, r15; unsigned __int16 *
0x180019094  sub     r12d, eax
0x180019097  lea     rcx, [rdi+rax*2]; unsigned __int16 *
0x18001909b  mov     edx, r12d; unsigned __int64
0x18001909e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800190a3  mov     rcx, r15; hMem
0x1800190a6  call    cs:__imp_LocalFree
0x1800190ac  call    cs:__imp_GetLastError
0x1800190b2  mov     r8d, eax
0x1800190b5  lea     rdx, aErrorGettingVa; "Error getting value: %d"
0x1800190bc  lea     rcx, aInfget2partstr_1; "InfGet2PartString"
0x1800190c3  call    ?WriteDbgTraceWarning@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800190c8  jmp     short loc_18001913C
0x1800190ca  mov     rcx, [rbx]; hMem
0x1800190cd  test    rcx, rcx
0x1800190d0  jz      short loc_1800190DB
0x1800190d2  call    cs:__imp_LocalFree
0x1800190d8  mov     [rbx], r13
0x1800190db  test    r15, r15
0x1800190de  jz      short loc_1800190E9
0x1800190e0  mov     rcx, r15; hMem
0x1800190e3  call    cs:__imp_LocalFree
0x1800190e9  test    rdi, rdi
0x1800190ec  jz      short loc_1800190F7
0x1800190ee  mov     rcx, rdi; hMem
0x1800190f1  call    cs:__imp_LocalFree
0x1800190f7  mov     dword ptr [rsi], 1
0x1800190fd  call    cs:__imp_GetLastError
0x180019103  mov     r8d, eax
0x180019106  lea     rdx, aErrorGettingVa; "Error getting value: %d"
0x18001910d  lea     rcx, aInfget2partstr_1; "InfGet2PartString"
0x180019114  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180019119  mov     ecx, 800300FDh; dwErrCode
0x18001911e  call    cs:__imp_SetLastError
0x180019124  jmp     short loc_18001913C
0x180019126  mov     r8, rdi
0x180019129  lea     rdx, aFieldWsHasNoVa; "Field %ws has no value."
0x180019130  lea     rcx, aInfget2partstr_1; "InfGet2PartString"
0x180019137  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001913c  add     rsp, 58h
0x180019140  pop     r15
0x180019142  pop     r14
0x180019144  pop     r13
0x180019146  pop     r12
0x180019148  pop     rdi
0x180019149  pop     rsi
0x18001914a  pop     rbx
0x18001914b  pop     rbp
0x18001914c  retn
```
