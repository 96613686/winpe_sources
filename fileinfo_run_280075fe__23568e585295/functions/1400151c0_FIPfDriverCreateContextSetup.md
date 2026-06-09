# FIPfDriverCreateContextSetup

- ea: `0x1400151c0`
- end: `0x140015392`
- name: `FIPfDriverCreateContextSetup`
- size: `466`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140017700`

## callees

- `0x1400151c0`

## import_xrefs

- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x1400151f2`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x1400151f2`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x140015384`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x140015384`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x140015277`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x1400152ea`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x140015277`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x1400152ea`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140015355`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14001536f`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140015355`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14001536f`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x14001523a`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x1400152bd`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x14001523a`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x1400152bd`

## pseudocode

```c
__int64 __fastcall FIPfDriverCreateContextSetup(__int64 a1)
{
  NTSTATUS Parameter; // ebx
  PVOID v3; // rdx
  PVOID EcpContext; // [rsp+68h] [rbp+10h] BYREF
  PVOID v6; // [rsp+70h] [rbp+18h] BYREF
  PECP_LIST EcpList; // [rsp+78h] [rbp+20h] BYREF

  EcpList = 0;
  EcpContext = 0;
  v6 = 0;
  Parameter = FltAllocateExtraCreateParameterList((PFLT_FILTER)FIGlobals, 0, &EcpList);
  if ( Parameter < 0 )
    goto LABEL_14;
  Parameter = FltAllocateExtraCreateParameterFromLookasideList(
                (PFLT_FILTER)FIGlobals,
                &CSE_ECP_TYPE_GUID,
                0x10u,
                0,
                0,
                qword_1400095C0,
                &EcpContext);
  if ( Parameter < 0
    || (*(_OWORD *)EcpContext = 0,
        *(_DWORD *)EcpContext = 1,
        Parameter = FltInsertExtraCreateParameter((PFLT_FILTER)FIGlobals, EcpList, EcpContext),
        Parameter < 0)
    || (EcpContext = 0,
        Parameter = FltAllocateExtraCreateParameterFromLookasideList(
                      (PFLT_FILTER)FIGlobals,
                      &GUID_ECP_PREFETCH_OPEN,
                      8u,
                      0,
                      0,
                      qword_1400095C0,
                      &v6),
        Parameter < 0)
    || (*(_QWORD *)v6 = 0, Parameter = FltInsertExtraCreateParameter((PFLT_FILTER)FIGlobals, EcpList, v6), Parameter < 0) )
  {
LABEL_14:
    v3 = v6;
  }
  else
  {
    v3 = 0;
    v6 = 0;
    Parameter = 0;
    *(_QWORD *)(a1 + 8) = EcpList;
    EcpList = 0;
  }
  if ( EcpContext )
  {
    FltFreeExtraCreateParameter((PFLT_FILTER)FIGlobals, EcpContext);
    v3 = v6;
  }
  if ( v3 )
    FltFreeExtraCreateParameter((PFLT_FILTER)FIGlobals, v3);
  if ( EcpList )
    FltFreeExtraCreateParameterList((PFLT_FILTER)FIGlobals, EcpList);
  return (unsigned int)Parameter;
}

```

## disassembly

```asm
0x1400151c0  mov     rax, rsp
0x1400151c3  push    rbx
0x1400151c4  sub     rsp, 50h
0x1400151c8  mov     [rax+8], rbp
0x1400151cc  lea     r8, [rax+20h]; EcpList
0x1400151d0  mov     [rax-10h], rsi
0x1400151d4  xor     edx, edx; Flags
0x1400151d6  xor     esi, esi
0x1400151d8  mov     [rax-18h], rdi
0x1400151dc  mov     rdi, rcx
0x1400151df  mov     [rax+20h], rsi
0x1400151e3  mov     rcx, cs:FIGlobals; Filter
0x1400151ea  mov     [rax+10h], rsi
0x1400151ee  mov     [rax+18h], rsi
0x1400151f2  call    cs:__imp_FltAllocateExtraCreateParameterList
0x1400151f9  nop     dword ptr [rax+rax+00h]
0x1400151fe  mov     ebx, eax
0x140015200  test    eax, eax
0x140015202  js      loc_140015344
0x140015208  mov     rcx, cs:FIGlobals; Filter
0x14001520f  lea     rax, [rsp+58h+arg_8]
0x140015214  mov     [rsp+58h+EcpContext], rax; EcpContext
0x140015219  lea     rbp, qword_1400095C0
0x140015220  mov     [rsp+58h+LookasideList], rbp; LookasideList
0x140015225  lea     rdx, CSE_ECP_TYPE_GUID; EcpType
0x14001522c  xor     r9d, r9d; Flags
0x14001522f  mov     [rsp+58h+CleanupCallback], rsi; CleanupCallback
0x140015234  mov     r8d, 10h; SizeOfContext
0x14001523a  call    cs:__imp_FltAllocateExtraCreateParameterFromLookasideList
0x140015241  nop     dword ptr [rax+rax+00h]
0x140015246  mov     ebx, eax
0x140015248  test    eax, eax
0x14001524a  js      loc_140015344
0x140015250  mov     rax, [rsp+58h+arg_8]
0x140015255  xorps   xmm0, xmm0
0x140015258  movups  xmmword ptr [rax], xmm0
0x14001525b  mov     rax, [rsp+58h+arg_8]
0x140015260  mov     dword ptr [rax], 1
0x140015266  mov     r8, [rsp+58h+arg_8]; EcpContext
0x14001526b  mov     rdx, [rsp+58h+EcpList]; EcpList
0x140015270  mov     rcx, cs:FIGlobals; Filter
0x140015277  call    cs:__imp_FltInsertExtraCreateParameter
0x14001527e  nop     dword ptr [rax+rax+00h]
0x140015283  mov     ebx, eax
0x140015285  test    eax, eax
0x140015287  js      loc_140015344
0x14001528d  mov     rcx, cs:FIGlobals; Filter
0x140015294  lea     rax, [rsp+58h+arg_10]
0x140015299  mov     [rsp+58h+EcpContext], rax; EcpContext
0x14001529e  lea     rdx, GUID_ECP_PREFETCH_OPEN; EcpType
0x1400152a5  mov     [rsp+58h+LookasideList], rbp; LookasideList
0x1400152aa  xor     r9d, r9d; Flags
0x1400152ad  mov     r8d, 8; SizeOfContext
0x1400152b3  mov     [rsp+58h+CleanupCallback], rsi; CleanupCallback
0x1400152b8  mov     [rsp+58h+arg_8], rsi
0x1400152bd  call    cs:__imp_FltAllocateExtraCreateParameterFromLookasideList
0x1400152c4  nop     dword ptr [rax+rax+00h]
0x1400152c9  mov     ebx, eax
0x1400152cb  test    eax, eax
0x1400152cd  js      short loc_140015344
0x1400152cf  mov     rax, [rsp+58h+arg_10]
0x1400152d4  xor     ecx, ecx
0x1400152d6  mov     [rax], rcx
0x1400152d9  mov     r8, [rsp+58h+arg_10]; EcpContext
0x1400152de  mov     rdx, [rsp+58h+EcpList]; EcpList
0x1400152e3  mov     rcx, cs:FIGlobals; Filter
0x1400152ea  call    cs:__imp_FltInsertExtraCreateParameter
0x1400152f1  nop     dword ptr [rax+rax+00h]
0x1400152f6  mov     ebx, eax
0x1400152f8  test    eax, eax
0x1400152fa  js      short loc_140015344
0x1400152fc  mov     rax, [rsp+58h+EcpList]
0x140015301  mov     edx, esi; EcpContext
0x140015303  mov     [rsp+58h+arg_10], rdx
0x140015308  mov     ebx, esi
0x14001530a  mov     [rdi+8], rax
0x14001530e  mov     [rsp+58h+EcpList], rsi
0x140015313  mov     rax, [rsp+58h+arg_8]
0x140015318  mov     rdi, [rsp+58h+var_18]
0x14001531d  mov     rsi, [rsp+58h+var_10]
0x140015322  mov     rbp, [rsp+58h+arg_0]
0x140015327  test    rax, rax
0x14001532a  jnz     short loc_14001534B
0x14001532c  test    rdx, rdx
0x14001532f  jnz     short loc_140015368
0x140015331  mov     rdx, [rsp+58h+EcpList]; EcpList
0x140015336  test    rdx, rdx
0x140015339  jnz     short loc_14001537D
0x14001533b  mov     eax, ebx
0x14001533d  add     rsp, 50h
0x140015341  pop     rbx
0x140015342  retn
0x140015344  mov     rdx, [rsp+58h+arg_10]
0x140015349  jmp     short loc_140015313
0x14001534b  mov     rcx, cs:FIGlobals; Filter
0x140015352  mov     rdx, rax; EcpContext
0x140015355  call    cs:__imp_FltFreeExtraCreateParameter
0x14001535c  nop     dword ptr [rax+rax+00h]
0x140015361  mov     rdx, [rsp+58h+arg_10]
0x140015366  jmp     short loc_14001532C
0x140015368  mov     rcx, cs:FIGlobals; Filter
0x14001536f  call    cs:__imp_FltFreeExtraCreateParameter
0x140015376  nop     dword ptr [rax+rax+00h]
0x14001537b  jmp     short loc_140015331
0x14001537d  mov     rcx, cs:FIGlobals; Filter
0x140015384  call    cs:__imp_FltFreeExtraCreateParameterList
0x14001538b  nop     dword ptr [rax+rax+00h]
0x140015390  jmp     short loc_14001533B
```
