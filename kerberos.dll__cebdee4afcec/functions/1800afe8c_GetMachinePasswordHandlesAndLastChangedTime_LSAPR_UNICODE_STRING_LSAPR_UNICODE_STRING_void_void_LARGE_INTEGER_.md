# GetMachinePasswordHandlesAndLastChangedTime(_LSAPR_UNICODE_STRING *,_LSAPR_UNICODE_STRING *,void * *,void * *,_LARGE_INTEGER *,int *,KerbMachinePasswordProtection *,int *,_UNICODE_STRING *)

- ea: `0x1800afe8c`
- end: `0x1800b00cc`
- name: `?GetMachinePasswordHandlesAndLastChangedTime@@YAJPEAU_LSAPR_UNICODE_STRING@@0PEAPEAX1PEAT_LARGE_INTEGER@@PEAHPEAW4KerbMachinePasswordProtection@@3PEAU_UNICODE_STRING@@@Z`
- size: `576`
- prototype: `__int64 __fastcall(struct _LSAPR_UNICODE_STRING *, struct _LSAPR_UNICODE_STRING *, void **, void **, union _LARGE_INTEGER *, int *, enum KerbMachinePasswordProtection *, int *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b1f98`

## callees

- `0x180035c10`
- `0x180070680`
- `0x18008b70c`
- `0x1800afd80`
- `0x1800afe8c`
- `0x1800b0164`

## import_xrefs

- `LSASRV!LsarOpenSecret` at `0x1800aff12`
- `LSASRV!LsarOpenSecret` at `0x1800aff4b`
- `LSASRV!LsarOpenSecret` at `0x1800aff12`
- `LSASRV!LsarOpenSecret` at `0x1800aff4b`
- `LSASRV!LsarCreateSecret` at `0x1800affb2`
- `LSASRV!LsarCreateSecret` at `0x1800afff0`
- `LSASRV!LsarCreateSecret` at `0x1800affb2`
- `LSASRV!LsarCreateSecret` at `0x1800afff0`
- `LSASRV!LsarQuerySecret` at `0x1800aff30`
- `LSASRV!LsarQuerySecret` at `0x1800aff70`
- `LSASRV!LsarQuerySecret` at `0x1800aff30`
- `LSASRV!LsarQuerySecret` at `0x1800aff70`

## string_xrefs

- `0x1800b0030`: `Failed to open LSA-bound machine secret: 0x%x`

## pseudocode

```c
__int64 __fastcall GetMachinePasswordHandlesAndLastChangedTime(
        struct _LSAPR_UNICODE_STRING *a1,
        struct _LSAPR_UNICODE_STRING *a2,
        void **a3,
        void **a4,
        union _LARGE_INTEGER *a5,
        int *a6,
        enum KerbMachinePasswordProtection *a7,
        int *a8,
        struct _UNICODE_STRING *a9)
{
  int Secret; // ebx
  int v14; // r14d
  __int64 v15; // r8
  int v16; // ecx
  int v17; // r8d
  LONGLONG v19; // [rsp+30h] [rbp-51h] BYREF
  struct _LSAPR_UNICODE_STRING *v20; // [rsp+38h] [rbp-49h]
  struct _LSAPR_CR_CIPHER_VALUE *v21; // [rsp+40h] [rbp-41h] BYREF
  struct _LSAPR_CR_CIPHER_VALUE *v22; // [rsp+48h] [rbp-39h] BYREF
  union _LARGE_INTEGER *v23; // [rsp+50h] [rbp-31h]
  int *v24; // [rsp+58h] [rbp-29h]
  struct _UNICODE_STRING *v25; // [rsp+60h] [rbp-21h] BYREF

  v23 = a5;
  v24 = a8;
  v25 = a9;
  v20 = a2;
  v19 = 0;
  v22 = 0;
  v21 = 0;
  *(_DWORD *)a7 = GetMachineIdentityIsolationStatus();
  Secret = LsarOpenSecret(KerbGlobalPolicyHandle, a2, 3, a4);
  if ( !Secret )
    Secret = LsarQuerySecret(*a4, 0, &v19, 0, 0);
  v14 = LsarOpenSecret(KerbGlobalPolicyHandle, a1, 3, a3);
  if ( !v14 )
    v14 = LsarQuerySecret(*a3, &v22, v23, &v21, 0);
  if ( !*(_DWORD *)a7 )
  {
    if ( Secret >= 0 )
      *a6 = 1;
    if ( v14 == -1073741772 )
    {
      if ( Secret < 0 )
        goto LABEL_27;
      v15 = 3936;
LABEL_22:
      KerbTracerT::Log(
        1,
        "GetMachinePasswordHandlesAndLastChangedTime",
        v15,
        "Failed to open LSA-bound machine secret: 0x%x",
        -1073741772);
      if ( (Microsoft_Windows_Security_KerberosEnableBits & 2) != 0 )
        McGenEventWrite_EtwEventWriteTransfer(v16, (unsigned int)EnforcedModeMustRejoinDomain, v17, 1, (__int64)&v25);
      Secret = -1073741816;
      goto LABEL_27;
    }
LABEL_25:
    if ( v14 >= 0 )
      goto LABEL_26;
    goto LABEL_27;
  }
  if ( *(_DWORD *)a7 == 1 )
  {
    if ( Secret == -1073741772 )
    {
      Secret = LsarCreateSecret(KerbGlobalPolicyHandle, v20, 983043, a4);
      *a6 = 1;
    }
    if ( v14 == -1073741772 )
    {
      if ( Secret < 0 )
        goto LABEL_27;
      v15 = 3955;
      goto LABEL_22;
    }
    goto LABEL_25;
  }
  if ( *(_DWORD *)a7 != 2 )
    goto LABEL_25;
  if ( Secret == -1073741772 )
  {
    Secret = LsarCreateSecret(KerbGlobalPolicyHandle, v20, 983043, a4);
    *a6 = 1;
  }
  if ( v14 >= 0 )
  {
    *a6 = 1;
LABEL_26:
    IsDefaultPasswordBeingChanged(v22, v21, v25, v24);
  }
LABEL_27:
  if ( KerbGlobalIsRunningIsolated && *(_DWORD *)a7 )
  {
    v14 = Secret;
    v23->QuadPart = v19;
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800afe8c  push    rbp
0x1800afe8e  push    rbx
0x1800afe8f  push    rsi
0x1800afe90  push    rdi
0x1800afe91  push    r12
0x1800afe93  push    r13
0x1800afe95  push    r14
0x1800afe97  push    r15
0x1800afe99  lea     rbp, [rsp-7]
0x1800afe9e  sub     rsp, 88h
0x1800afea5  mov     rax, cs:__security_cookie
0x1800afeac  xor     rax, rsp
0x1800afeaf  mov     [rbp+3Fh+var_50], rax
0x1800afeb3  mov     rax, [rbp+3Fh+arg_20]
0x1800afeb7  xor     r14d, r14d
0x1800afeba  mov     r15, [rbp+3Fh+arg_28]
0x1800afebe  mov     r13, r9
0x1800afec1  mov     r12, [rbp+3Fh+arg_30]
0x1800afec5  mov     rdi, r8
0x1800afec8  mov     [rbp+3Fh+var_70], rax
0x1800afecc  mov     rbx, rdx
0x1800afecf  mov     rax, [rbp+3Fh+arg_38]
0x1800afed6  mov     rsi, rcx
0x1800afed9  mov     [rbp+3Fh+var_68], rax
0x1800afedd  mov     rax, [rbp+3Fh+arg_40]
0x1800afee4  mov     [rbp+3Fh+var_60], rax
0x1800afee8  mov     [rbp+3Fh+var_88], rdx
0x1800afeec  mov     [rbp+3Fh+var_90], r14
0x1800afef0  mov     [rbp+3Fh+var_78], r14
0x1800afef4  mov     [rbp+3Fh+var_80], r14
0x1800afef8  call    ?GetMachineIdentityIsolationStatus@@YA?AW4KerbMachinePasswordProtection@@XZ; GetMachineIdentityIsolationStatus(void)
0x1800afefd  mov     [r12], eax
0x1800aff01  lea     r8d, [r14+3]
0x1800aff05  mov     rcx, cs:?KerbGlobalPolicyHandle@@3PEAXEA; void * KerbGlobalPolicyHandle
0x1800aff0c  mov     r9, r13
0x1800aff0f  mov     rdx, rbx
0x1800aff12  call    cs:__imp_LsarOpenSecret
0x1800aff18  mov     ebx, eax
0x1800aff1a  test    eax, eax
0x1800aff1c  jnz     short loc_1800AFF38
0x1800aff1e  mov     rcx, [r13+0]
0x1800aff22  lea     r8, [rbp+3Fh+var_90]
0x1800aff26  xor     r9d, r9d
0x1800aff29  mov     [rsp+0C0h+var_A0], r14
0x1800aff2e  xor     edx, edx
0x1800aff30  call    cs:__imp_LsarQuerySecret
0x1800aff36  mov     ebx, eax
0x1800aff38  mov     rcx, cs:?KerbGlobalPolicyHandle@@3PEAXEA; void * KerbGlobalPolicyHandle
0x1800aff3f  mov     r9, rdi
0x1800aff42  mov     r8d, 3
0x1800aff48  mov     rdx, rsi
0x1800aff4b  call    cs:__imp_LsarOpenSecret
0x1800aff51  mov     r14d, eax
0x1800aff54  test    eax, eax
0x1800aff56  jnz     short loc_1800AFF79
0x1800aff58  mov     r8, [rbp+3Fh+var_70]
0x1800aff5c  lea     r9, [rbp+3Fh+var_80]
0x1800aff60  mov     rcx, [rdi]
0x1800aff63  lea     rdx, [rbp+3Fh+var_78]
0x1800aff67  mov     [rsp+0C0h+var_A0], 0
0x1800aff70  call    cs:__imp_LsarQuerySecret
0x1800aff76  mov     r14d, eax
0x1800aff79  mov     ecx, [r12]
0x1800aff7d  test    ecx, ecx
0x1800aff7f  jz      loc_1800B0010
0x1800aff85  sub     ecx, 1
0x1800aff88  jz      short loc_1800AFFCE
0x1800aff8a  cmp     ecx, 1
0x1800aff8d  jnz     loc_1800B0071
0x1800aff93  mov     esi, 0C0000034h
0x1800aff98  mov     edi, ecx
0x1800aff9a  cmp     ebx, esi
0x1800aff9c  jnz     short loc_1800AFFBD
0x1800aff9e  mov     rdx, [rbp+3Fh+var_88]
0x1800affa2  mov     r9, r13
0x1800affa5  mov     rcx, cs:?KerbGlobalPolicyHandle@@3PEAXEA; void * KerbGlobalPolicyHandle
0x1800affac  mov     r8d, 0F0003h
0x1800affb2  call    cs:__imp_LsarCreateSecret
0x1800affb8  mov     ebx, eax
0x1800affba  mov     [r15], edi
0x1800affbd  test    r14d, r14d
0x1800affc0  js      loc_1800B008B
0x1800affc6  mov     [r15], edi
0x1800affc9  jmp     loc_1800B0076
0x1800affce  mov     esi, 0C0000034h
0x1800affd3  mov     edi, 1
0x1800affd8  cmp     ebx, esi
0x1800affda  jnz     short loc_1800AFFFB
0x1800affdc  mov     rdx, [rbp+3Fh+var_88]
0x1800affe0  mov     r9, r13
0x1800affe3  mov     rcx, cs:?KerbGlobalPolicyHandle@@3PEAXEA; void * KerbGlobalPolicyHandle
0x1800affea  mov     r8d, 0F0003h
0x1800afff0  call    cs:__imp_LsarCreateSecret
0x1800afff6  mov     ebx, eax
0x1800afff8  mov     [r15], edi
0x1800afffb  cmp     r14d, esi
0x1800afffe  jnz     short loc_1800B0071
0x1800b0000  test    ebx, ebx
0x1800b0002  js      loc_1800B008B
0x1800b0008  mov     r8d, 0F73h
0x1800b000e  jmp     short loc_1800B0030
0x1800b0010  mov     edi, 1
0x1800b0015  test    ebx, ebx
0x1800b0017  js      short loc_1800B001C
0x1800b0019  mov     [r15], edi
0x1800b001c  mov     esi, 0C0000034h
0x1800b0021  cmp     r14d, esi
0x1800b0024  jnz     short loc_1800B0071
0x1800b0026  test    ebx, ebx
0x1800b0028  js      short loc_1800B008B
0x1800b002a  mov     r8d, 0F60h
0x1800b0030  lea     r9, aFailedToOpenLs; "Failed to open LSA-bound machine secret"...
0x1800b0037  mov     dword ptr [rsp+0C0h+var_A0], esi
0x1800b003b  lea     rdx, aGetmachinepass; "GetMachinePasswordHandlesAndLastChanged"...
0x1800b0042  mov     ecx, edi
0x1800b0044  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800b0049  test    cs:Microsoft_Windows_Security_KerberosEnableBits, 2
0x1800b0050  jz      short loc_1800B006A
0x1800b0052  lea     rax, [rbp+3Fh+var_60]
0x1800b0056  mov     r9d, edi
0x1800b0059  lea     rdx, EnforcedModeMustRejoinDomain
0x1800b0060  mov     [rsp+0C0h+var_A0], rax
0x1800b0065  call    McGenEventWrite_EtwEventWriteTransfer
0x1800b006a  mov     ebx, 0C0000008h
0x1800b006f  jmp     short loc_1800B008B
0x1800b0071  test    r14d, r14d
0x1800b0074  js      short loc_1800B008B
0x1800b0076  mov     r9, [rbp+3Fh+var_68]; int *
0x1800b007a  mov     r8, [rbp+3Fh+var_60]; struct _UNICODE_STRING *
0x1800b007e  mov     rdx, [rbp+3Fh+var_80]; struct _LSAPR_CR_CIPHER_VALUE *
0x1800b0082  mov     rcx, [rbp+3Fh+var_78]; struct _LSAPR_CR_CIPHER_VALUE *
0x1800b0086  call    ?IsDefaultPasswordBeingChanged@@YAXPEAU_LSAPR_CR_CIPHER_VALUE@@0PEAU_UNICODE_STRING@@PEAH@Z; IsDefaultPasswordBeingChanged(_LSAPR_CR_CIPHER_VALUE *,_LSAPR_CR_CIPHER_VALUE *,_UNICODE_STRING *,int *)
0x1800b008b  cmp     cs:?KerbGlobalIsRunningIsolated@@3HA, 0; int KerbGlobalIsRunningIsolated
0x1800b0092  jz      short loc_1800B00A9
0x1800b0094  cmp     dword ptr [r12], 0
0x1800b0099  jz      short loc_1800B00A9
0x1800b009b  mov     rcx, [rbp+3Fh+var_70]
0x1800b009f  mov     r14d, ebx
0x1800b00a2  mov     rax, [rbp+3Fh+var_90]
0x1800b00a6  mov     [rcx], rax
0x1800b00a9  mov     eax, r14d
0x1800b00ac  mov     rcx, [rbp+3Fh+var_50]
0x1800b00b0  xor     rcx, rsp; StackCookie
0x1800b00b3  call    __security_check_cookie
0x1800b00b8  add     rsp, 88h
0x1800b00bf  pop     r15
0x1800b00c1  pop     r14
0x1800b00c3  pop     r13
0x1800b00c5  pop     r12
0x1800b00c7  pop     rdi
0x1800b00c8  pop     rsi
0x1800b00c9  pop     rbx
0x1800b00ca  pop     rbp
0x1800b00cb  retn
```
