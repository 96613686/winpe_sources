# PsmSrvRegisterProcess

- ea: `0x180019670`
- end: `0x180019801`
- name: `PsmSrvRegisterProcess`
- size: `401`
- prototype: `__int64 __fastcall(__int64, void *, __int64, __int64, __int64, PSID SourceSid, int, __int64, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation`

## callees

- `0x18000102c`
- `0x180013658`
- `0x1800180d0`
- `0x1800192fc`
- `0x180019670`
- `0x18001b7e0`
- `0x18001c10c`
- `0x18001d34c`

## pseudocode

```c
__int64 __fastcall PsmSrvRegisterProcess(
        __int64 a1,
        void *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        PSID SourceSid,
        int a7,
        __int64 a8,
        int a9)
{
  __int64 v11; // r8
  BOOL v12; // ecx
  int v13; // ebx
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  int v18[4]; // [rsp+30h] [rbp-268h] BYREF
  __int64 v19[68]; // [rsp+40h] [rbp-258h] BYREF

  memset_0(v19, 0, sizeof(v19));
  v12 = a5 == 0;
  if ( v12 != (SourceSid == 0) || v12 != (a8 == -1) )
    goto LABEL_12;
  if ( a5 )
  {
    v13 = PsmpAppIdentityValidateEx(SourceSid);
    if ( v13 < 0 )
      goto LABEL_13;
    if ( a9 != 8 || (a8 & 0xF000000000000000uLL) == 0x2000000000000000LL )
    {
      PsmpAppIdentityInitialize(SourceSid, (__int64)v19);
      goto LABEL_10;
    }
LABEL_12:
    v13 = -1073741776;
    goto LABEL_13;
  }
  if ( a7 )
    goto LABEL_12;
LABEL_10:
  v13 = PsmRegisterApplicationProcessEx(a2, a4);
  if ( v13 >= 0 )
    return 0;
LABEL_13:
  if ( (unsigned int)dword_18003F080 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18003F080, 3, v11) )
  {
    v18[0] = v13;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v14,
      (unsigned int)byte_180039101,
      v15,
      v16,
      (__int64)v18);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180019670  mov     [rsp+arg_0], rbx
0x180019675  push    rbp
0x180019676  push    r12
0x180019678  push    r13
0x18001967a  push    r14
0x18001967c  push    r15
0x18001967e  sub     rsp, 270h
0x180019685  mov     rax, cs:__security_cookie
0x18001968c  xor     rax, rsp
0x18001968f  mov     [rsp+298h+var_38], rax
0x180019697  mov     rbp, [rsp+298h+arg_20]
0x18001969f  lea     rcx, [rsp+298h+var_258]; void *
0x1800196a4  mov     r14, [rsp+298h+SourceSid]
0x1800196ac  mov     r12d, r8d
0x1800196af  mov     r15, rdx
0x1800196b2  mov     r8d, 220h; Size
0x1800196b8  xor     edx, edx; Val
0x1800196ba  mov     r13, r9
0x1800196bd  call    memset_0
0x1800196c2  xor     ecx, ecx
0x1800196c4  test    rbp, rbp
0x1800196c7  setz    cl
0x1800196ca  xor     eax, eax
0x1800196cc  test    r14, r14
0x1800196cf  setz    al
0x1800196d2  cmp     ecx, eax
0x1800196d4  jnz     loc_180019797
0x1800196da  xor     eax, eax
0x1800196dc  cmp     [rsp+298h+arg_38], 0FFFFFFFFFFFFFFFFh
0x1800196e5  setz    al
0x1800196e8  cmp     ecx, eax
0x1800196ea  jnz     loc_180019797
0x1800196f0  test    rbp, rbp
0x1800196f3  jnz     short loc_180019706
0x1800196f5  cmp     [rsp+298h+arg_30], ebp
0x1800196fc  jnz     loc_180019797
0x180019702  xor     edx, edx
0x180019704  jmp     short loc_180019775
0x180019706  mov     edx, [rsp+298h+arg_40]
0x18001970d  mov     r8, rbp
0x180019710  mov     rcx, r14; Sid
0x180019713  call    PsmpAppIdentityValidateEx
0x180019718  mov     ebx, eax
0x18001971a  test    eax, eax
0x18001971c  js      short loc_18001979C
0x18001971e  cmp     [rsp+298h+arg_40], 8
0x180019726  jnz     short loc_18001974C
0x180019728  mov     rax, [rsp+298h+arg_38]
0x180019730  mov     rcx, 0F000000000000000h
0x18001973a  and     rax, rcx
0x18001973d  mov     rcx, 2000000000000000h
0x180019747  cmp     rax, rcx
0x18001974a  jnz     short loc_180019797
0x18001974c  mov     r8d, [rsp+298h+arg_40]
0x180019754  lea     rax, [rsp+298h+var_258]
0x180019759  mov     edx, [rsp+298h+arg_30]
0x180019760  mov     r9, rbp
0x180019763  mov     rcx, r14; SourceSid
0x180019766  mov     [rsp+298h+var_278], rax; __int64
0x18001976b  call    PsmpAppIdentityInitialize
0x180019770  lea     rdx, [rsp+298h+var_258]
0x180019775  mov     r8, [rsp+298h+arg_38]
0x18001977d  mov     r9d, r12d
0x180019780  mov     rcx, r15; ProcessHandle
0x180019783  mov     [rsp+298h+var_278], r13; __int64
0x180019788  call    PsmRegisterApplicationProcessEx
0x18001978d  mov     ebx, eax
0x18001978f  test    eax, eax
0x180019791  js      short loc_18001979C
0x180019793  xor     ebx, ebx
0x180019795  jmp     short loc_1800197D6
0x180019797  mov     ebx, 0C0000030h
0x18001979c  mov     eax, cs:dword_18003F080
0x1800197a2  cmp     eax, 4
0x1800197a5  jbe     short loc_1800197D6
0x1800197a7  mov     edx, 3
0x1800197ac  lea     rcx, dword_18003F080
0x1800197b3  call    _tlgKeywordOn
0x1800197b8  test    al, al
0x1800197ba  jz      short loc_1800197D6
0x1800197bc  lea     rax, [rsp+298h+var_268]
0x1800197c1  mov     [rsp+298h+var_268], ebx
0x1800197c5  lea     rdx, byte_180039101
0x1800197cc  mov     [rsp+298h+var_278], rax
0x1800197d1  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800197d6  mov     eax, ebx
0x1800197d8  mov     rcx, [rsp+298h+var_38]
0x1800197e0  xor     rcx, rsp; StackCookie
0x1800197e3  call    __security_check_cookie
0x1800197e8  mov     rbx, [rsp+298h+arg_0]
0x1800197f0  add     rsp, 270h
0x1800197f7  pop     r15
0x1800197f9  pop     r14
0x1800197fb  pop     r13
0x1800197fd  pop     r12
0x1800197ff  pop     rbp
0x180019800  retn
```
