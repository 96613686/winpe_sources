# SignMessageXmlDSig(RTSecurityContextBase *,CACSendParameters *,AP<char> &)

- ea: `0x18001958c`
- end: `0x18001965d`
- name: `?SignMessageXmlDSig@@YAJPEAVRTSecurityContextBase@@PEAVCACSendParameters@@AEAV?$AP@D@@@Z`
- size: `209`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c888`

## callees

- `0x180013c74`
- `0x18001958c`
- `0x180026010`

## import_xrefs

- `mqsec!MQSec_CreateXmlDSig` at `0x18001962a`
- `mqsec!MQSec_CreateXmlDSig` at `0x18001962a`

## string_xrefs

- `0x18001963c`: `rt/SignMessageXml`

## pseudocode

```c
__int64 __fastcall SignMessageXmlDSig(_DWORD *a1, __int64 a2, __int64 a3)
{
  __int64 result; // rax
  __int64 *v7; // rax
  __int64 v8; // r12
  __int64 *v9; // rax
  __int64 v10; // r15
  int *v11; // rax
  int v12; // esi
  int v13; // edi
  unsigned int v14; // ebp
  int v15; // ebx
  __int64 v16; // rax
  int XmlDSig; // eax
  unsigned int v18; // ebx

  result = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)a1 + 8LL))(a1);
  if ( (int)result >= 0 )
  {
    v7 = *(__int64 **)(a2 + 80);
    if ( v7 )
      v8 = *v7;
    else
      v8 = 0;
    v9 = *(__int64 **)(a2 + 368);
    if ( v9 )
      v10 = *v9;
    else
      v10 = 0;
    v11 = *(int **)(a2 + 216);
    v12 = *(_DWORD *)(a2 + 376);
    v13 = a1[16];
    v14 = *(_DWORD *)(a2 + 88);
    v15 = *v11;
    v16 = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)a1 + 16LL))(a1);
    XmlDSig = MQSec_CreateXmlDSig(v16, &g_QMId, v14, v8, v12, v10, v15, v13, a3);
    v18 = XmlDSig;
    if ( XmlDSig < 0 )
      LogMsgHR(XmlDSig, (wchar_t *)L"rt/SignMessageXml", 0x95u);
    return v18;
  }
  return result;
}

```

## disassembly

```asm
0x18001958c  push    rbx
0x18001958e  push    rbp
0x18001958f  push    rsi
0x180019590  push    rdi
0x180019591  push    r12
0x180019593  push    r13
0x180019595  push    r14
0x180019597  push    r15
0x180019599  sub     rsp, 58h
0x18001959d  mov     rax, [rcx]
0x1800195a0  mov     r13, r8
0x1800195a3  mov     rbp, rdx
0x1800195a6  mov     r14, rcx
0x1800195a9  mov     rax, [rax+8]
0x1800195ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800195b2  test    eax, eax
0x1800195b4  js      loc_18001964C
0x1800195ba  mov     rax, [rbp+50h]
0x1800195be  test    rax, rax
0x1800195c1  jnz     short loc_1800195C8
0x1800195c3  xor     r12d, r12d
0x1800195c6  jmp     short loc_1800195CB
0x1800195c8  mov     r12, [rax]
0x1800195cb  mov     rax, [rbp+170h]
0x1800195d2  test    rax, rax
0x1800195d5  jnz     short loc_1800195DC
0x1800195d7  xor     r15d, r15d
0x1800195da  jmp     short loc_1800195DF
0x1800195dc  mov     r15, [rax]
0x1800195df  mov     rax, [rbp+0D8h]
0x1800195e6  mov     rcx, r14
0x1800195e9  mov     esi, [rbp+178h]
0x1800195ef  mov     edi, [r14+40h]
0x1800195f3  mov     ebp, [rbp+58h]
0x1800195f6  mov     ebx, [rax]
0x1800195f8  mov     rax, [r14]
0x1800195fb  mov     rax, [rax+10h]
0x1800195ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019604  mov     [rsp+98h+var_58], r13
0x180019609  lea     rdx, ?g_QMId@@3U_GUID@@A; _GUID g_QMId
0x180019610  mov     [rsp+98h+var_60], edi
0x180019614  mov     r9, r12
0x180019617  mov     [rsp+98h+var_68], ebx
0x18001961b  mov     r8d, ebp
0x18001961e  mov     [rsp+98h+var_70], r15
0x180019623  mov     rcx, rax
0x180019626  mov     [rsp+98h+var_78], esi
0x18001962a  call    cs:__imp_?MQSec_CreateXmlDSig@@YAJ_KPEBU_GUID@@KPEBEK2KKAEAV?$AP@D@@@Z; MQSec_CreateXmlDSig(unsigned __int64,_GUID const *,ulong,uchar const *,ulong,uchar const *,ulong,ulong,AP<char> &)
0x180019630  mov     ebx, eax
0x180019632  test    eax, eax
0x180019634  jns     short loc_18001964A
0x180019636  mov     r8d, 95h; unsigned __int16
0x18001963c  lea     rdx, aRtSignmessagex; "rt/SignMessageXml"
0x180019643  mov     ecx, eax; int
0x180019645  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18001964a  mov     eax, ebx
0x18001964c  add     rsp, 58h
0x180019650  pop     r15
0x180019652  pop     r14
0x180019654  pop     r13
0x180019656  pop     r12
0x180019658  pop     rdi
0x180019659  pop     rsi
0x18001965a  pop     rbp
0x18001965b  pop     rbx
0x18001965c  retn
```
