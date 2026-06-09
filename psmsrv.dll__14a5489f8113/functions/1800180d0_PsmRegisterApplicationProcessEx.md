# PsmRegisterApplicationProcessEx

- ea: `0x1800180d0`
- end: `0x18001848e`
- name: `PsmRegisterApplicationProcessEx`
- size: `958`
- prototype: `__int64 __usercall@<rax>(HANDLE ProcessHandle@<rcx>, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x180019670`
- `0x18001e20c`

## callees

- `0x180001580`
- `0x18000171c`
- `0x180003ec8`
- `0x180013610`
- `0x1800137a4`
- `0x1800180d0`
- `0x1800184a0`
- `0x1800192fc`
- `0x18001b7e0`
- `0x18001c10c`

## import_xrefs

- `ntdll!NtClose` at `0x1800182cd`
- `ntdll!NtClose` at `0x1800182cd`
- `ntdll!NtOpenProcessTokenEx` at `0x18001836b`
- `ntdll!NtOpenProcessTokenEx` at `0x18001836b`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001821f`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001821f`
- `ext-ms-win-core-psm-service-l1-1-2!PsmHamRegisterProcess` at `0x18001842d`
- `ext-ms-win-core-psm-service-l1-1-2!PsmHamRegisterProcess` at `0x18001842d`

## pseudocode

```c
__int64 __fastcall PsmRegisterApplicationProcessEx(
        HANDLE ProcessHandle,
        const unsigned __int16 *a2,
        __int64 a3,
        int a4,
        __int64 a5)
{
  const unsigned __int16 *v5; // rdi
  __int64 v8; // rsi
  int IsPackageFamilyNameEnabled; // ebx
  HANDLE v11; // r15
  DWORD ProcessId; // eax
  int v13; // eax
  BOOL v15; // r12d
  bool v16; // sf
  HANDLE Process; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v18; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v20; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *v21; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v22; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD v23[34]; // [rsp+70h] [rbp-90h] BYREF
  struct _EVENT_DATA_DESCRIPTOR ValueName[2]; // [rsp+290h] [rbp+190h] BYREF
  __int64 *v25; // [rsp+2B0h] [rbp+1B0h]
  __int64 v26; // [rsp+2B8h] [rbp+1B8h]
  char v27[16]; // [rsp+2C0h] [rbp+1C0h] BYREF
  __int64 *v28; // [rsp+2D0h] [rbp+1D0h]
  __int64 v29; // [rsp+2D8h] [rbp+1D8h]
  __int64 **v30; // [rsp+2E0h] [rbp+1E0h]
  __int64 v31; // [rsp+2E8h] [rbp+1E8h]
  __int64 *v32; // [rsp+2F0h] [rbp+1F0h]
  __int64 v33; // [rsp+2F8h] [rbp+1F8h]
  HANDLE *p_Process; // [rsp+300h] [rbp+200h]
  __int64 v35; // [rsp+308h] [rbp+208h]
  char *v36; // [rsp+310h] [rbp+210h]
  int v37; // [rsp+318h] [rbp+218h]
  int v38; // [rsp+31Ch] [rbp+21Ch]
  struct _EVENT_DATA_DESCRIPTOR v39; // [rsp+320h] [rbp+220h] BYREF

  v5 = (const unsigned __int16 *)v23;
  v20 = a3;
  Process = ProcessHandle;
  v8 = -1;
  v22 = a5;
  v18 = -1;
  Handle = 0;
  memset_0(v23, 0, sizeof(v23));
  if ( (unsigned int)dword_18003F080 > 4 && tlgKeywordOn((__int64)&dword_18003F080, 1) )
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18003F080, (unsigned __int8 *)byte_18003801D, 0, 0, 2u, &v39);
  if ( (a4 & 0xFFFFFF00) == 0 && ((a4 & 0xC) == 0 || (a4 & 1) == 0) )
  {
    if ( (a4 & 0x40) == 0 )
    {
      v21 = &v18;
LABEL_18:
      v15 = a2 == 0;
      if ( (v20 == -1) != v15 )
      {
        IsPackageFamilyNameEnabled = -1073741776;
        goto LABEL_6;
      }
      IsPackageFamilyNameEnabled = NtOpenProcessTokenEx(ProcessHandle, 8u, 0, &Handle);
      if ( IsPackageFamilyNameEnabled < 0 )
        goto LABEL_6;
      if ( (int)PsmpQueryClientApplicationInformation(Process, Handle, v23, v21) >= 0 != v15 )
      {
        v8 = v18;
        IsPackageFamilyNameEnabled = -1073741776;
        goto LABEL_6;
      }
      if ( a2 )
      {
        v8 = v20;
        v5 = a2;
      }
      else
      {
        v8 = v18;
        v5 = (const unsigned __int16 *)v23;
      }
      IsPackageFamilyNameEnabled = HamOptInPsmKeyToPackageFamilyName(v5 + 4, (unsigned __int16 *)ValueName);
      if ( IsPackageFamilyNameEnabled
        || (IsPackageFamilyNameEnabled = HamOptInIsPackageFamilyNameEnabledEx((LPCWSTR)ValueName)) != 0 )
      {
        v11 = Process;
        v16 = IsPackageFamilyNameEnabled < 0;
        if ( IsPackageFamilyNameEnabled <= 0 )
          goto LABEL_32;
        IsPackageFamilyNameEnabled = (unsigned __int16)IsPackageFamilyNameEnabled | 0xC0070000;
      }
      else
      {
        v11 = Process;
        IsPackageFamilyNameEnabled = PsmRegisterApplicationProcessHamByPass(
                                       (_DWORD)Process,
                                       (_DWORD)Handle,
                                       (_DWORD)v5,
                                       v8,
                                       a4,
                                       v22);
      }
      v16 = IsPackageFamilyNameEnabled < 0;
LABEL_32:
      if ( !v16 )
        goto LABEL_10;
      goto LABEL_7;
    }
    if ( (a4 & 0xFFFFFF9F) == 0 )
    {
      v21 = 0;
      goto LABEL_18;
    }
  }
  IsPackageFamilyNameEnabled = -1073741582;
LABEL_6:
  v11 = Process;
LABEL_7:
  if ( (unsigned int)dword_18003F080 > 4 && tlgKeywordOn((__int64)&dword_18003F080, 3) )
  {
    LODWORD(v20) = IsPackageFamilyNameEnabled;
    v25 = &v20;
    v26 = 4;
    tlgCreate1Sz_wchar_t((__int64)v27, (char *)v5 + 8);
    v22 = v8;
    v28 = &v22;
    v29 = 8;
    ProcessId = GetProcessId(v11);
    v31 = 4;
    LODWORD(v21) = ProcessId;
    LODWORD(v18) = a4;
    v30 = &v21;
    v33 = 4;
    v32 = &v18;
    LODWORD(Process) = *(_DWORD *)v5;
    p_Process = &Process;
    v36 = (char *)(v5 + 236);
    v13 = *((unsigned __int8 *)v5 + 473);
    v35 = 4;
    v38 = 0;
    v37 = 4 * v13 + 8;
    tlgWriteTransfer_EventWriteTransfer(
      (__int64)&dword_18003F080,
      (unsigned __int8 *)byte_18003817F,
      0,
      0,
      9u,
      ValueName);
  }
LABEL_10:
  if ( Handle )
    NtClose(Handle);
  return (unsigned int)IsPackageFamilyNameEnabled;
}

```

## disassembly

```asm
0x1800180d0  push    rbp
0x1800180d2  push    rbx
0x1800180d3  push    rsi
0x1800180d4  push    rdi
0x1800180d5  push    r12
0x1800180d7  push    r13
0x1800180d9  push    r14
0x1800180db  push    r15
0x1800180dd  lea     rbp, [rsp-258h]
0x1800180e5  sub     rsp, 358h
0x1800180ec  mov     rax, cs:__security_cookie
0x1800180f3  xor     rax, rsp
0x1800180f6  mov     [rbp+290h+var_50], rax
0x1800180fd  mov     rax, [rbp+290h+arg_20]
0x180018104  lea     rdi, [rsp+390h+var_320]
0x180018109  mov     [rsp+390h+var_340], r8
0x18001810e  mov     r13, rdx
0x180018111  mov     rbx, rcx
0x180018114  mov     [rsp+390h+Process], rcx
0x180018119  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001811d  mov     [rsp+390h+var_330], rax
0x180018122  xor     edx, edx; Val
0x180018124  mov     [rsp+390h+var_350], rsi
0x180018129  mov     r8d, 220h; Size
0x18001812f  mov     [rsp+390h+var_360], 0
0x180018134  lea     rcx, [rsp+390h+var_320]; void *
0x180018139  mov     [rsp+390h+Handle], 0
0x180018142  mov     r14d, r9d
0x180018145  call    memset_0
0x18001814a  mov     eax, cs:dword_18003F080
0x180018150  cmp     eax, 4
0x180018153  jbe     short loc_180018195
0x180018155  lea     edx, [rsi+2]
0x180018158  lea     rcx, dword_18003F080
0x18001815f  call    _tlgKeywordOn
0x180018164  test    al, al
0x180018166  jz      short loc_180018195
0x180018168  lea     rax, [rbp+290h+var_70]
0x18001816f  xor     r9d, r9d
0x180018172  mov     [rsp+390h+var_368], rax
0x180018177  lea     rdx, byte_18003801D
0x18001817e  xor     r8d, r8d
0x180018181  mov     [rsp+390h+var_370], 2
0x180018189  lea     rcx, dword_18003F080
0x180018190  call    _tlgWriteTransfer_EventWriteTransfer
0x180018195  test    r14d, 0FFFFFF00h
0x18001819c  jz      loc_1800182F8
0x1800181a2  mov     ebx, 0C00000F2h
0x1800181a7  mov     r15, [rsp+390h+Process]
0x1800181ac  mov     eax, cs:dword_18003F080
0x1800181b2  mov     r13d, 4
0x1800181b8  cmp     eax, r13d
0x1800181bb  jbe     loc_1800182C3
0x1800181c1  lea     edx, [r13-1]
0x1800181c5  lea     rcx, dword_18003F080
0x1800181cc  call    _tlgKeywordOn
0x1800181d1  test    al, al
0x1800181d3  jz      loc_1800182C3
0x1800181d9  lea     rax, [rsp+390h+var_340]
0x1800181de  mov     dword ptr [rsp+390h+var_340], ebx
0x1800181e2  lea     rdx, [rdi+8]
0x1800181e6  mov     [rbp+290h+var_E0], rax
0x1800181ed  lea     rcx, [rbp+290h+var_D0]
0x1800181f4  mov     [rbp+290h+var_D8], r13
0x1800181fb  call    _tlgCreate1Sz_wchar_t
0x180018200  lea     rax, [rsp+390h+var_330]
0x180018205  mov     [rsp+390h+var_330], rsi
0x18001820a  mov     rcx, r15; Process
0x18001820d  mov     [rbp+290h+var_C0], rax
0x180018214  mov     [rbp+290h+var_B8], 8
0x18001821f  call    cs:__imp_GetProcessId
0x180018225  xor     r9d, r9d
0x180018228  mov     [rbp+290h+var_A8], r13
0x18001822f  mov     dword ptr [rsp+390h+var_338], eax
0x180018233  lea     rdx, byte_18003817F
0x18001823a  lea     rax, [rsp+390h+var_338]
0x18001823f  mov     dword ptr [rsp+390h+var_350], r14d
0x180018244  mov     [rbp+290h+var_B0], rax
0x18001824b  lea     rcx, dword_18003F080
0x180018252  lea     rax, [rsp+390h+var_350]
0x180018257  mov     [rbp+290h+var_98], r13
0x18001825e  mov     [rbp+290h+var_A0], rax
0x180018265  xor     r8d, r8d
0x180018268  mov     eax, [rdi]
0x18001826a  mov     dword ptr [rsp+390h+Process], eax
0x18001826e  lea     rax, [rsp+390h+Process]
0x180018273  mov     [rbp+290h+var_90], rax
0x18001827a  lea     rax, [rdi+1D8h]
0x180018281  mov     [rbp+290h+var_80], rax
0x180018288  movzx   eax, byte ptr [rax+1]
0x18001828c  mov     [rbp+290h+var_88], r13
0x180018293  mov     [rbp+290h+var_74], 0
0x18001829d  lea     eax, ds:8[rax*4]
0x1800182a4  mov     [rbp+290h+var_78], eax
0x1800182aa  lea     rax, [rbp+290h+ValueName]
0x1800182b1  mov     [rsp+390h+var_368], rax
0x1800182b6  mov     [rsp+390h+var_370], 9
0x1800182be  call    _tlgWriteTransfer_EventWriteTransfer
0x1800182c3  mov     rcx, [rsp+390h+Handle]; Handle
0x1800182c8  test    rcx, rcx
0x1800182cb  jz      short loc_1800182D3
0x1800182cd  call    cs:__imp_NtClose
0x1800182d3  mov     eax, ebx
0x1800182d5  mov     rcx, [rbp+290h+var_50]
0x1800182dc  xor     rcx, rsp; StackCookie
0x1800182df  call    __security_check_cookie
0x1800182e4  add     rsp, 358h
0x1800182eb  pop     r15
0x1800182ed  pop     r14
0x1800182ef  pop     r13
0x1800182f1  pop     r12
0x1800182f3  pop     rdi
0x1800182f4  pop     rsi
0x1800182f5  pop     rbx
0x1800182f6  pop     rbp
0x1800182f7  retn
0x1800182f8  test    r14b, 0Ch
0x1800182fc  setnz   cl
0x1800182ff  test    r14b, 1
0x180018303  setnz   al
0x180018306  test    al, cl
0x180018308  jnz     loc_1800181A2
0x18001830e  mov     r15d, r14d
0x180018311  and     r15d, 40h
0x180018315  jz      short loc_18001832F
0x180018317  test    r14d, 0FFFFFF9Fh
0x18001831e  jnz     loc_1800181A2
0x180018324  mov     [rsp+390h+var_338], 0
0x18001832d  jmp     short loc_180018339
0x18001832f  lea     rax, [rsp+390h+var_350]
0x180018334  mov     [rsp+390h+var_338], rax
0x180018339  xor     r12d, r12d
0x18001833c  test    r13, r13
0x18001833f  setz    r12b
0x180018343  xor     eax, eax
0x180018345  cmp     [rsp+390h+var_340], rsi
0x18001834a  setz    al
0x18001834d  cmp     eax, r12d
0x180018350  jz      short loc_18001835C
0x180018352  mov     ebx, 0C0000030h
0x180018357  jmp     loc_1800181A7
0x18001835c  xor     r8d, r8d; HandleAttributes
0x18001835f  lea     r9, [rsp+390h+Handle]; TokenHandle
0x180018364  mov     rcx, rbx; ProcessHandle
0x180018367  lea     edx, [r8+8]; DesiredAccess
0x18001836b  call    cs:__imp_NtOpenProcessTokenEx
0x180018371  mov     ebx, eax
0x180018373  test    eax, eax
0x180018375  js      loc_1800181A7
0x18001837b  mov     r9, [rsp+390h+var_338]
0x180018380  lea     r8, [rsp+390h+var_320]
0x180018385  mov     rdx, [rsp+390h+Handle]; TokenHandle
0x18001838a  mov     rcx, [rsp+390h+Process]; ProcessHandle
0x18001838f  call    PsmpQueryClientApplicationInformation
0x180018394  not     eax
0x180018396  shr     eax, 1Fh
0x180018399  cmp     eax, r12d
0x18001839c  jz      short loc_1800183AD
0x18001839e  mov     rsi, [rsp+390h+var_350]
0x1800183a3  mov     ebx, 0C0000030h
0x1800183a8  jmp     loc_1800181A7
0x1800183ad  test    r13, r13
0x1800183b0  jz      short loc_1800183BC
0x1800183b2  mov     rsi, [rsp+390h+var_340]
0x1800183b7  mov     rdi, r13
0x1800183ba  jmp     short loc_1800183C6
0x1800183bc  mov     rsi, [rsp+390h+var_350]
0x1800183c1  lea     rdi, [rsp+390h+var_320]
0x1800183c6  lea     rcx, [rdi+8]; unsigned __int16 *
0x1800183ca  lea     rdx, [rbp+290h+ValueName]; unsigned __int16 *
0x1800183d1  call    ?HamOptInPsmKeyToPackageFamilyName@@YAKPEBGPEAG@Z; HamOptInPsmKeyToPackageFamilyName(ushort const *,ushort *)
0x1800183d6  mov     ebx, eax
0x1800183d8  test    eax, eax
0x1800183da  jnz     loc_18001846F
0x1800183e0  lea     r8, [rsp+390h+var_360]
0x1800183e5  lea     rcx, [rbp+290h+ValueName]; lpValueName
0x1800183ec  call    HamOptInIsPackageFamilyNameEnabledEx
0x1800183f1  mov     ebx, eax
0x1800183f3  test    eax, eax
0x1800183f5  jnz     short loc_18001846F
0x1800183f7  cmp     [rsp+390h+var_360], al
0x1800183fb  jz      short loc_180018444
0x1800183fd  cmp     byte ptr [rdi+21Ch], 8
0x180018404  jz      short loc_180018444
0x180018406  test    r15d, r15d
0x180018409  jnz     short loc_180018444
0x18001840b  mov     rax, [rsp+390h+var_330]
0x180018410  mov     r9, rsi
0x180018413  mov     r15, [rsp+390h+Process]
0x180018418  mov     r8, rdi
0x18001841b  mov     rdx, [rsp+390h+Handle]
0x180018420  mov     rcx, r15
0x180018423  mov     [rsp+390h+var_368], rax
0x180018428  mov     [rsp+390h+var_370], r14d
0x18001842d  call    cs:__imp_PsmHamRegisterProcess
0x180018433  mov     ebx, eax
0x180018435  test    eax, eax
0x180018437  js      loc_1800181AC
0x18001843d  xor     ebx, ebx
0x18001843f  jmp     loc_1800182C3
0x180018444  mov     rax, [rsp+390h+var_330]
0x180018449  mov     r9, rsi
0x18001844c  mov     r15, [rsp+390h+Process]
0x180018451  mov     r8, rdi
0x180018454  mov     rdx, [rsp+390h+Handle]
0x180018459  mov     rcx, r15
0x18001845c  mov     [rsp+390h+var_368], rax
0x180018461  mov     [rsp+390h+var_370], r14d
0x180018466  call    PsmRegisterApplicationProcessHamByPass
0x18001846b  mov     ebx, eax
0x18001846d  jmp     short loc_180018481
0x18001846f  mov     r15, [rsp+390h+Process]
0x180018474  test    ebx, ebx
0x180018476  jle     short loc_180018483
0x180018478  movzx   ebx, bx
0x18001847b  or      ebx, 0C0070000h
0x180018481  test    ebx, ebx
0x180018483  jns     loc_1800182C3
0x180018489  jmp     loc_1800181AC
```
