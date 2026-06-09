# MvProcessConfigXml(ushort const *,ushort const *,ProvStateContext const *,long (*)(void *,IDomNode *,IWAPDPUHelper *,IConfigManager2 *),int,ushort * *,ushort * *,int *)

- ea: `0x180031764`
- end: `0x18003189e`
- name: `?MvProcessConfigXml@@YAJPEBG0PEBVProvStateContext@@P6AJPEAXPEAUIDomNode@@PEAUIWAPDPUHelper@@PEAUIConfigManager2@@@ZHPEAPEAG7PEAH@Z`
- size: `314`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const struct ProvStateContext *, int (*)(void *, struct IDomNode *, struct IWAPDPUHelper *, struct IConfigManager2 *), int, unsigned __int16 **, unsigned __int16 **, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180018f74`

## callees

- `0x1800010c8`
- `0x1800098dc`
- `0x180031764`
- `0x1800318a4`
- `0x180043750`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800317ac`
- `OLEAUT32!__imp_SysFreeString` at `0x1800317bc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800317ac`
- `OLEAUT32!__imp_SysFreeString` at `0x1800317bc`

## pseudocode

```c
__int64 __fastcall MvProcessConfigXml(
        const unsigned __int16 *a1,
        char *a2,
        const struct ProvStateContext *a3,
        int (*a4)(void *, struct IDomNode *, struct IWAPDPUHelper *, struct IConfigManager2 *),
        int a5,
        unsigned __int16 **a6,
        unsigned __int16 **a7,
        int *a8)
{
  int v11; // edi
  int v12; // eax
  unsigned int v13; // ebx
  int v15; // [rsp+20h] [rbp-79h]
  int *v16; // [rsp+38h] [rbp-61h]
  int v17; // [rsp+40h] [rbp-59h] BYREF
  int v18; // [rsp+44h] [rbp-55h] BYREF
  int *v19; // [rsp+48h] [rbp-51h]
  struct _EVENT_DATA_DESCRIPTOR v20; // [rsp+50h] [rbp-49h] BYREF
  int *v21; // [rsp+70h] [rbp-29h]
  __int64 v22; // [rsp+78h] [rbp-21h]
  int *v23; // [rsp+80h] [rbp-19h]
  __int64 v24; // [rsp+88h] [rbp-11h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+3Fh]

  v19 = a8;
  v11 = 0;
  while ( 1 )
  {
    SysFreeString(*a6);
    *a6 = 0;
    SysFreeString(*a7);
    v16 = v19;
    *a7 = 0;
    v12 = MvProcessConfigXmlInternal(
            (__int64)a1,
            a2,
            (__int64)a3,
            (__int64)MvDpuPostProcessCallback,
            a5,
            (char **)a6,
            a7,
            v16);
    v13 = v12;
    if ( v12 >= 0 )
      break;
    if ( (unsigned int)dword_18005A000 > 2 )
    {
      v17 = v12;
      v18 = v11;
      v24 = 4;
      v23 = &v17;
      v22 = 4;
      v21 = &v18;
      tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18005A000, (unsigned __int8 *)byte_18004FE73, 0, 0, 4u, &v20);
    }
    if ( (unsigned int)++v11 >= 3 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x139,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionutil.cpp",
        (const char *)v13,
        v15);
      return v13;
    }
  }
  return v13;
}

```

## disassembly

```asm
0x180031764  mov     [rsp-8+arg_18], rbx
0x180031769  push    rbp
0x18003176a  push    rsi
0x18003176b  push    rdi
0x18003176c  push    r12
0x18003176e  push    r13
0x180031770  push    r14
0x180031772  push    r15
0x180031774  lea     rbp, [rsp-7]
0x180031779  sub     rsp, 0A0h
0x180031780  mov     rax, cs:__security_cookie
0x180031787  xor     rax, rsp
0x18003178a  mov     [rbp+37h+var_40], rax
0x18003178e  mov     rax, [rbp+37h+arg_38]
0x180031792  mov     r13, r8
0x180031795  mov     rsi, [rbp+37h+arg_28]
0x180031799  mov     r12, rdx
0x18003179c  mov     r14, [rbp+37h+arg_30]
0x1800317a0  mov     r15, rcx
0x1800317a3  mov     [rbp+37h+var_88], rax
0x1800317a7  xor     edi, edi
0x1800317a9  mov     rcx, [rsi]; bstrString
0x1800317ac  call    cs:__imp_SysFreeString
0x1800317b2  mov     qword ptr [rsi], 0
0x1800317b9  mov     rcx, [r14]; bstrString
0x1800317bc  call    cs:__imp_SysFreeString
0x1800317c2  mov     rax, [rbp+37h+var_88]
0x1800317c6  lea     r9, MvDpuPostProcessCallback
0x1800317cd  mov     [rsp+0D0h+var_98], rax
0x1800317d2  mov     r8, r13
0x1800317d5  mov     eax, [rbp+37h+arg_20]
0x1800317d8  mov     rdx, r12
0x1800317db  mov     [rsp+0D0h+var_A0], r14
0x1800317e0  mov     rcx, r15
0x1800317e3  mov     [rsp+0D0h+var_A8], rsi
0x1800317e8  mov     [rsp+0D0h+var_B0], eax
0x1800317ec  mov     qword ptr [r14], 0
0x1800317f3  call    MvProcessConfigXmlInternal
0x1800317f8  mov     ebx, eax
0x1800317fa  test    eax, eax
0x1800317fc  jns     short loc_180031875
0x1800317fe  mov     ecx, cs:dword_18005A000
0x180031804  cmp     ecx, 2
0x180031807  jbe     short loc_180031852
0x180031809  mov     [rbp+37h+var_90], eax
0x18003180c  lea     rdx, byte_18004FE73
0x180031813  mov     ecx, 4
0x180031818  mov     [rbp+37h+var_8C], edi
0x18003181b  lea     rax, [rbp+37h+var_90]
0x18003181f  mov     [rbp+37h+var_48], rcx
0x180031823  mov     [rbp+37h+var_50], rax
0x180031827  xor     r9d, r9d
0x18003182a  lea     rax, [rbp+37h+var_8C]
0x18003182e  mov     [rbp+37h+var_58], rcx
0x180031832  mov     [rbp+37h+var_60], rax
0x180031836  xor     r8d, r8d
0x180031839  lea     rax, [rbp+37h+var_80]
0x18003183d  mov     [rsp+0D0h+var_A8], rax
0x180031842  mov     [rsp+0D0h+var_B0], ecx; int
0x180031846  lea     rcx, dword_18005A000
0x18003184d  call    _tlgWriteTransfer_EventWriteTransfer
0x180031852  inc     edi
0x180031854  cmp     edi, 3
0x180031857  jb      loc_1800317A9
0x18003185d  mov     rcx, [rbp+3Fh]; this
0x180031861  lea     r8, aOnecoreuapAdmi_24; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180031868  mov     r9d, ebx; char *
0x18003186b  mov     edx, 139h; void *
0x180031870  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031875  mov     eax, ebx
0x180031877  mov     rcx, [rbp+37h+var_40]
0x18003187b  xor     rcx, rsp; StackCookie
0x18003187e  call    __security_check_cookie
0x180031883  mov     rbx, [rsp+0D0h+arg_18]
0x18003188b  add     rsp, 0A0h
0x180031892  pop     r15
0x180031894  pop     r14
0x180031896  pop     r13
0x180031898  pop     r12
0x18003189a  pop     rdi
0x18003189b  pop     rsi
0x18003189c  pop     rbp
0x18003189d  retn
```
