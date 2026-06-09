# SvcWorker::GetSvcWorker(void *,ICorSvcLogger *,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort *,LogicalImage *)

- ea: `0x18002b988`
- end: `0x18002bbf1`
- name: `?GetSvcWorker@SvcWorker@@SAPEAUICorSvcWorker@@PEAXPEAUICorSvcLogger@@PEBG222HPEAGPEAVLogicalImage@@@Z`
- size: `617`
- prototype: `struct ICorSvcWorker *__fastcall(void *, struct ICorSvcLogger *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, bool, BSTR pbstr, struct LogicalImage *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800289bc`

## callees

- `0x18002a784`
- `0x18002b988`
- `0x18002f260`
- `0x180034fd4`
- `0x1800366a8`
- `0x18003f280`

## import_xrefs

- `KERNEL32!OpenEventW` at `0x18002b9fe`
- `KERNEL32!OpenEventW` at `0x18002b9fe`
- `KERNEL32!GetCurrentProcessId` at `0x18002bb03`
- `KERNEL32!GetCurrentProcessId` at `0x18002bb03`
- `KERNEL32!CloseHandle` at `0x18002bbb4`
- `KERNEL32!CloseHandle` at `0x18002bbb4`
- `OLEAUT32!__imp_SysAllocString` at `0x18002bab0`
- `OLEAUT32!__imp_SysAllocString` at `0x18002bab0`
- `OLEAUT32!__imp_SysFreeString` at `0x18002bb62`
- `OLEAUT32!__imp_SysFreeString` at `0x18002bb62`
- `OLEAUT32!__imp_SysStringLen` at `0x18002b9e9`
- `OLEAUT32!__imp_SysStringLen` at `0x18002b9e9`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
struct ICorSvcWorker *__fastcall SvcWorker::GetSvcWorker(
        void *a1,
        struct ICorSvcLogger *a2,
        wchar_t *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        bool a7,
        BSTR pbstr,
        struct LogicalImage *a9)
{
  BOOL v13; // esi
  int v14; // r12d
  HANDLE v15; // rdi
  int v16; // eax
  __int64 *CorSvcBindToUnregisteredWorker; // r14
  OLECHAR *v18; // r15
  BOOL v19; // esi
  __int64 v20; // rbx
  DWORD CurrentProcessId; // eax
  int v22; // eax
  __int64 v23; // rbx
  void *v25; // [rsp+50h] [rbp-39h] BYREF
  __int64 v26; // [rsp+58h] [rbp-31h] BYREF
  int v27; // [rsp+60h] [rbp-29h]
  __int64 v28; // [rsp+68h] [rbp-21h]
  int v29; // [rsp+70h] [rbp-19h]
  OLECHAR *v30; // [rsp+78h] [rbp-11h]
  BOOL v31; // [rsp+80h] [rbp-9h]
  __int64 *v32; // [rsp+88h] [rbp-1h]
  BOOL v33; // [rsp+90h] [rbp+7h]

  v13 = CLRConfig::GetConfigValue(
          (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::EXTERNAL_NGenLocalWorker,
          (bool)a2,
          &a7) == 1;
  v28 = -1;
  v14 = 0;
  v29 = 0;
  if ( SysStringLen(pbstr) )
  {
    v15 = OpenEventW(0x100000u, 1, pbstr);
    v28 = (__int64)v15;
    if ( v15 == (HANDLE)-1LL )
      goto LABEL_6;
  }
  else
  {
    v15 = 0;
    v28 = 0;
  }
  v14 = 1;
  v29 = 1;
LABEL_6:
  if ( v13 )
  {
    v16 = CCorSvcBindToWorker::CreateObject(&IID_ICorSvcBindToWorker, &v25);
    if ( v16 < 0 )
      ThrowHR(v16);
    CorSvcBindToUnregisteredWorker = (__int64 *)v25;
  }
  else
  {
    CorSvcBindToUnregisteredWorker = (__int64 *)SvcWorker::GetCorSvcBindToUnregisteredWorker(
                                                  a1,
                                                  a2,
                                                  a3,
                                                  a4,
                                                  a5,
                                                  a6,
                                                  v15,
                                                  a9);
  }
  v32 = CorSvcBindToUnregisteredWorker;
  v33 = CorSvcBindToUnregisteredWorker != 0;
  v26 = 0;
  v27 = 0;
  v18 = 0;
  v30 = 0;
  v19 = 0;
  v31 = 0;
  if ( a3 )
  {
    v18 = SysAllocString(a3);
    v30 = v18;
    v19 = v18 != 0;
    v31 = v19;
  }
  v25 = &v26;
  if ( v27 )
  {
    if ( v26 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    v27 = 0;
  }
  v26 = 0;
  v20 = *CorSvcBindToUnregisteredWorker;
  CurrentProcessId = GetCurrentProcessId();
  v22 = (*(__int64 (__fastcall **)(__int64 *, OLECHAR *, _QWORD, BSTR, struct ICorSvcLogger *, __int64 *))(v20 + 24))(
          CorSvcBindToUnregisteredWorker,
          v18,
          CurrentProcessId,
          pbstr,
          a2,
          &v26);
  if ( v22 < 0 )
    ThrowHR(v22);
  v23 = v26;
  v27 = 0;
  if ( v19 )
  {
    SysFreeString(v18);
    v31 = 0;
  }
  if ( v27 )
  {
    if ( v26 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    v27 = 0;
  }
  if ( CorSvcBindToUnregisteredWorker )
  {
    (*(void (__fastcall **)(__int64 *))(*CorSvcBindToUnregisteredWorker + 16))(CorSvcBindToUnregisteredWorker);
    v33 = 0;
  }
  if ( v14 )
  {
    if ( v15 )
      CloseHandle(v15);
    v29 = 0;
  }
  return (struct ICorSvcWorker *)v23;
}

```

## disassembly

```asm
0x18002b988  mov     rax, rsp
0x18002b98b  mov     [rax+8], rbx
0x18002b98f  mov     [rax+18h], rsi
0x18002b993  mov     [rax+20h], rdi
0x18002b997  mov     [rax+10h], rdx
0x18002b99b  push    rbp
0x18002b99c  push    r12
0x18002b99e  push    r13
0x18002b9a0  push    r14
0x18002b9a2  push    r15
0x18002b9a4  lea     rbp, [rax-37h]
0x18002b9a8  sub     rsp, 90h
0x18002b9af  mov     r14, r9
0x18002b9b2  mov     rbx, r8
0x18002b9b5  mov     r13, rdx
0x18002b9b8  mov     r15, rcx
0x18002b9bb  and     [rbp+2Fh+var_70], 0
0x18002b9bf  lea     r8, [rbp+2Fh+arg_30]; bool *
0x18002b9c3  lea     rcx, ?EXTERNAL_NGenLocalWorker@CLRConfig@@2UConfigDWORDInfo@1@B; struct CLRConfig::ConfigDWORDInfo *
0x18002b9ca  call    ?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@_NPEA_N@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &,bool,bool *)
0x18002b9cf  xor     esi, esi
0x18002b9d1  lea     edi, [rsi+1]
0x18002b9d4  cmp     eax, edi
0x18002b9d6  cmovz   esi, edi
0x18002b9d9  or      [rbp+2Fh+var_50], 0FFFFFFFFFFFFFFFFh
0x18002b9de  xor     r12d, r12d
0x18002b9e1  mov     [rbp+2Fh+var_48], r12d
0x18002b9e5  mov     rcx, [rbp+2Fh+pbstr]; pbstr
0x18002b9e9  call    cs:__imp_SysStringLen
0x18002b9ef  test    eax, eax
0x18002b9f1  jz      short loc_18002BA13
0x18002b9f3  mov     r8, [rbp+2Fh+pbstr]; lpName
0x18002b9f7  mov     edx, edi; bInheritHandle
0x18002b9f9  mov     ecx, 100000h; dwDesiredAccess
0x18002b9fe  call    cs:__imp_OpenEventW
0x18002ba04  mov     rdi, rax
0x18002ba07  mov     [rbp+2Fh+var_50], rax
0x18002ba0b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002ba0f  jz      short loc_18002BA23
0x18002ba11  jmp     short loc_18002BA19
0x18002ba13  xor     edi, edi
0x18002ba15  mov     [rbp+2Fh+var_50], rdi
0x18002ba19  mov     r12d, 1
0x18002ba1f  mov     [rbp+2Fh+var_48], r12d
0x18002ba23  test    esi, esi
0x18002ba25  jz      short loc_18002BA45
0x18002ba27  lea     rdx, [rbp+2Fh+var_68]; void **
0x18002ba2b  lea     rcx, IID_ICorSvcBindToWorker; struct _GUID *
0x18002ba32  call    ?CreateObject@CCorSvcBindToWorker@@SAJAEBU_GUID@@PEAPEAX@Z; CCorSvcBindToWorker::CreateObject(_GUID const &,void * *)
0x18002ba37  test    eax, eax
0x18002ba39  js      loc_18002BBE9
0x18002ba3f  mov     r14, [rbp+2Fh+var_68]
0x18002ba43  jmp     short loc_18002BA79
0x18002ba45  mov     rax, [rbp+2Fh+arg_40]
0x18002ba49  mov     [rsp+0B0h+var_78], rax; struct LogicalImage *
0x18002ba4e  mov     [rsp+0B0h+var_80], rdi; void *
0x18002ba53  mov     rax, [rbp+2Fh+arg_28]
0x18002ba57  mov     [rsp+0B0h+var_88], rax; unsigned __int16 *
0x18002ba5c  mov     rax, [rbp+2Fh+arg_20]
0x18002ba60  mov     [rsp+0B0h+var_90], rax; unsigned __int16 *
0x18002ba65  mov     r9, r14; unsigned __int16 *
0x18002ba68  mov     r8, rbx; unsigned __int16 *
0x18002ba6b  mov     rdx, r13; struct ICorSvcLogger *
0x18002ba6e  mov     rcx, r15; void *
0x18002ba71  call    ?GetCorSvcBindToUnregisteredWorker@SvcWorker@@KAPEAUICorSvcBindToWorker@@PEAXPEAUICorSvcLogger@@PEBG2220PEAVLogicalImage@@@Z; SvcWorker::GetCorSvcBindToUnregisteredWorker(void *,ICorSvcLogger *,ushort const *,ushort const *,ushort const *,ushort const *,void *,LogicalImage *)
0x18002ba76  mov     r14, rax
0x18002ba79  mov     [rbp+2Fh+var_30], r14
0x18002ba7d  and     [rbp+2Fh+var_28], 0
0x18002ba81  xor     r13d, r13d
0x18002ba84  test    r14, r14
0x18002ba87  lea     eax, [r13+1]
0x18002ba8b  cmovnz  r13d, eax
0x18002ba8f  mov     [rbp+2Fh+var_28], r13d
0x18002ba93  and     [rbp+2Fh+var_60], 0
0x18002ba98  and     [rbp+2Fh+var_58], 0
0x18002ba9c  xor     r15d, r15d
0x18002ba9f  mov     [rbp+2Fh+var_40], r15
0x18002baa3  xor     esi, esi
0x18002baa5  mov     [rbp+2Fh+var_38], esi
0x18002baa8  test    rbx, rbx
0x18002baab  jz      short loc_18002BACB
0x18002baad  mov     rcx, rbx; psz
0x18002bab0  call    cs:__imp_SysAllocString
0x18002bab6  mov     r15, rax
0x18002bab9  mov     [rbp+2Fh+var_40], rax
0x18002babd  test    rax, rax
0x18002bac0  lea     ebx, [rsi+1]
0x18002bac3  cmovnz  esi, ebx
0x18002bac6  mov     [rbp+2Fh+var_38], esi
0x18002bac9  jmp     short loc_18002BAD0
0x18002bacb  mov     ebx, 1
0x18002bad0  lea     rax, [rbp+2Fh+var_60]
0x18002bad4  mov     [rbp+2Fh+var_68], rax
0x18002bad8  cmp     [rbp+2Fh+var_58], 0
0x18002badc  jz      short loc_18002BAF8
0x18002bade  mov     rcx, [rbp+2Fh+var_60]
0x18002bae2  test    rcx, rcx
0x18002bae5  jz      short loc_18002BAF4
0x18002bae7  mov     rax, [rcx]
0x18002baea  mov     rax, [rax+10h]
0x18002baee  call    cs:__guard_dispatch_icall_fptr
0x18002baf4  and     [rbp+2Fh+var_58], 0
0x18002baf8  and     [rbp+2Fh+var_60], 0
0x18002bafd  mov     [rbp+2Fh+var_70], ebx
0x18002bb00  mov     rbx, [r14]
0x18002bb03  call    cs:__imp_GetCurrentProcessId
0x18002bb09  mov     r8d, eax
0x18002bb0c  lea     rax, [rbp+2Fh+var_60]
0x18002bb10  mov     [rsp+0B0h+var_88], rax
0x18002bb15  mov     rax, [rbp+2Fh+arg_8]
0x18002bb19  mov     [rsp+0B0h+var_90], rax
0x18002bb1e  mov     r9, [rbp+2Fh+pbstr]
0x18002bb22  mov     rdx, r15
0x18002bb25  mov     rcx, r14
0x18002bb28  mov     rax, [rbx+18h]
0x18002bb2c  call    cs:__guard_dispatch_icall_fptr
0x18002bb32  test    eax, eax
0x18002bb34  js      loc_18002BBE1
0x18002bb3a  mov     ecx, 1
0x18002bb3f  mov     eax, ecx
0x18002bb41  and     eax, 0FFFFFFFEh
0x18002bb44  mov     [rbp+2Fh+var_70], eax
0x18002bb47  mov     eax, [rbp+2Fh+var_58]
0x18002bb4a  mov     rbx, [rbp+2Fh+var_60]
0x18002bb4e  test    rbx, rbx
0x18002bb51  cmovnz  eax, ecx
0x18002bb54  mov     [rbp+2Fh+var_58], eax
0x18002bb57  and     [rbp+2Fh+var_58], 0
0x18002bb5b  test    esi, esi
0x18002bb5d  jz      short loc_18002BB6F
0x18002bb5f  mov     rcx, r15; bstrString
0x18002bb62  call    cs:__imp_SysFreeString
0x18002bb68  xor     esi, esi
0x18002bb6a  mov     [rbp+2Fh+var_38], esi
0x18002bb6d  jmp     short loc_18002BB71
0x18002bb6f  xor     esi, esi
0x18002bb71  cmp     [rbp+2Fh+var_58], esi
0x18002bb74  jz      short loc_18002BB8F
0x18002bb76  mov     rcx, [rbp+2Fh+var_60]
0x18002bb7a  test    rcx, rcx
0x18002bb7d  jz      short loc_18002BB8C
0x18002bb7f  mov     rax, [rcx]
0x18002bb82  mov     rax, [rax+10h]
0x18002bb86  call    cs:__guard_dispatch_icall_fptr
0x18002bb8c  mov     [rbp+2Fh+var_58], esi
0x18002bb8f  test    r13d, r13d
0x18002bb92  jz      short loc_18002BBA7
0x18002bb94  mov     rax, [r14]
0x18002bb97  mov     rcx, r14
0x18002bb9a  mov     rax, [rax+10h]
0x18002bb9e  call    cs:__guard_dispatch_icall_fptr
0x18002bba4  mov     [rbp+2Fh+var_28], esi
0x18002bba7  test    r12d, r12d
0x18002bbaa  jz      short loc_18002BBBD
0x18002bbac  test    rdi, rdi
0x18002bbaf  jz      short loc_18002BBBA
0x18002bbb1  mov     rcx, rdi; hObject
0x18002bbb4  call    cs:__imp_CloseHandle
0x18002bbba  mov     [rbp+2Fh+var_48], esi
0x18002bbbd  mov     rax, rbx
0x18002bbc0  lea     r11, [rsp+0B0h+var_20]
0x18002bbc8  mov     rbx, [r11+30h]
0x18002bbcc  mov     rsi, [r11+40h]
0x18002bbd0  mov     rdi, [r11+48h]
0x18002bbd4  mov     rsp, r11
0x18002bbd7  pop     r15
0x18002bbd9  pop     r14
0x18002bbdb  pop     r13
0x18002bbdd  pop     r12
0x18002bbdf  pop     rbp
0x18002bbe0  retn
0x18002bbe1  mov     ecx, eax; int
0x18002bbe3  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18002bbe9  mov     ecx, eax; int
0x18002bbeb  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
```
