# MQSec_CreateXmlDSig(unsigned __int64,_GUID const *,ulong,uchar const *,ulong,uchar const *,ulong,ulong,AP<char> &)

- ea: `0x180019750`
- end: `0x18001993f`
- name: `?MQSec_CreateXmlDSig@@YAJ_KPEBU_GUID@@KPEBEK2KKAEAV?$AP@D@@@Z`
- size: `495`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800172f8`
- `0x180017f18`
- `0x180019234`
- `0x1800193e8`
- `0x180019600`
- `0x180019750`
- `0x180019a74`
- `0x180019b94`
- `0x18001a208`
- `0x18001a88c`
- `0x18002e29c`

## import_xrefs

- `msvcrt!free` at `0x18001990f`
- `msvcrt!free` at `0x180019924`
- `msvcrt!free` at `0x18001990f`
- `msvcrt!free` at `0x180019924`

## string_xrefs

- `0x1800197d8`: `extension@`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall MQSec_CreateXmlDSig(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned __int8 *a6,
        unsigned int a7,
        int a8,
        _QWORD *a9)
{
  char *v12; // rsi
  __int64 v13; // r14
  char *v14; // rdi
  __int64 v15; // rbx
  __int64 v17; // [rsp+28h] [rbp-B1h]
  __int64 v18; // [rsp+28h] [rbp-B1h]
  char **v19; // [rsp+30h] [rbp-A9h] BYREF
  __int64 v20; // [rsp+38h] [rbp-A1h] BYREF
  __int64 v21; // [rsp+40h] [rbp-99h] BYREF
  _BYTE v22[8]; // [rsp+48h] [rbp-91h] BYREF
  __int128 v23; // [rsp+50h] [rbp-89h]
  __int64 v24; // [rsp+60h] [rbp-79h]
  char *v25; // [rsp+68h] [rbp-71h]
  char *v26; // [rsp+70h] [rbp-69h]
  char *v27; // [rsp+80h] [rbp-59h] BYREF
  char *v28; // [rsp+88h] [rbp-51h] BYREF
  int v29; // [rsp+90h] [rbp-49h]
  const char *v30; // [rsp+98h] [rbp-41h]
  _BYTE v31[32]; // [rsp+A0h] [rbp-39h] BYREF
  __int64 v32; // [rsp+C0h] [rbp-19h]
  char *v33; // [rsp+C8h] [rbp-11h]
  int v34; // [rsp+D0h] [rbp-9h]
  __int64 v35; // [rsp+D8h] [rbp-1h]

  v12 = (char *)ComposeMimeAttachmentUri("body@");
  v25 = v12;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 32));
  v13 = NewXdsReference(a3, a4, a7, v12, v17);
  v21 = v13;
  v14 = (char *)ComposeMimeAttachmentUri("extension@");
  v26 = v14;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 32));
  v15 = NewXdsReference(a5, a6, a7, v14, v18);
  v20 = v15;
  v23 = 0;
  v24 = 0;
  if ( v13 )
  {
    v19 = (char **)v13;
    std::vector<CXdsReferenceInput *>::push_back(v22, &v19);
    v21 = 0;
  }
  if ( v15 )
  {
    v19 = (char **)v15;
    std::vector<CXdsReferenceInput *>::push_back(v22, &v19);
    v20 = 0;
  }
  v27 = newstr(0);
  v19 = &v28;
  v28 = newstr(0);
  v29 = 32772;
  v30 = "http://www.w3.org/2000/02/xmldsig#dsa";
  std::vector<CXdsReferenceInput *>::vector<CXdsReferenceInput *>(v31, v22);
  v32 = 0;
  v33 = newstr(0);
  v34 = a8;
  v35 = a1;
  *a9 = CXdsSignature::SignatureElement((CXdsSignature *)&v27);
  CXdsSignature::~CXdsSignature((CXdsSignature *)&v27);
  std::vector<CXdsReferenceInput *>::_Tidy(v22);
  P<CXdsReferenceInput>::~P<CXdsReferenceInput>(&v20);
  free(v14);
  P<CXdsReferenceInput>::~P<CXdsReferenceInput>(&v21);
  free(v12);
  return 0;
}

```

## disassembly

```asm
0x180019750  push    rbp
0x180019752  push    rbx
0x180019753  push    rsi
0x180019754  push    rdi
0x180019755  push    r12
0x180019757  push    r14
0x180019759  push    r15
0x18001975b  lea     rbp, [rsp-7]
0x180019760  sub     rsp, 0E0h
0x180019767  mov     rdi, r9
0x18001976a  mov     r14d, r8d
0x18001976d  mov     rbx, rdx
0x180019770  mov     r15, rcx
0x180019773  lea     rcx, aBody; "body@"
0x18001977a  call    ComposeMimeAttachmentUri
0x18001977f  mov     rsi, rax
0x180019782  mov     [rbp+37h+var_A8], rax
0x180019786  lea     r12, WPP_GLOBAL_Control
0x18001978d  mov     rcx, cs:WPP_GLOBAL_Control
0x180019794  cmp     rcx, r12
0x180019797  jz      short loc_1800197B6
0x180019799  test    byte ptr [rcx+10Ch], 4
0x1800197a0  jz      short loc_1800197B6
0x1800197a2  mov     edx, 0Dh
0x1800197a7  mov     r9, rax
0x1800197aa  mov     rcx, [rcx+100h]; LoggerHandle
0x1800197b1  call    WPP_SF_s
0x1800197b6  mov     [rsp+110h+var_F0], rsi; char *
0x1800197bb  mov     r9, r15
0x1800197be  mov     r8d, [rbp+37h+arg_30]; unsigned int
0x1800197c2  mov     rdx, rdi; unsigned __int8 *
0x1800197c5  mov     ecx, r14d; unsigned int
0x1800197c8  call    NewXdsReference
0x1800197cd  mov     r14, rax
0x1800197d0  mov     [rsp+110h+var_D0], rax
0x1800197d5  mov     rdx, rbx
0x1800197d8  lea     rcx, aExtension; "extension@"
0x1800197df  call    ComposeMimeAttachmentUri
0x1800197e4  mov     rdi, rax
0x1800197e7  mov     [rbp+37h+var_A0], rax
0x1800197eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800197f2  cmp     rcx, r12
0x1800197f5  jz      short loc_180019814
0x1800197f7  test    byte ptr [rcx+10Ch], 4
0x1800197fe  jz      short loc_180019814
0x180019800  mov     edx, 0Eh
0x180019805  mov     r9, rax
0x180019808  mov     rcx, [rcx+100h]; LoggerHandle
0x18001980f  call    WPP_SF_s
0x180019814  mov     [rsp+110h+var_F0], rdi; char *
0x180019819  mov     r9, r15
0x18001981c  mov     r8d, [rbp+37h+arg_30]; unsigned int
0x180019820  mov     rdx, [rbp+37h+arg_28]; unsigned __int8 *
0x180019824  mov     ecx, [rbp+37h+arg_20]; unsigned int
0x180019827  call    NewXdsReference
0x18001982c  mov     rbx, rax
0x18001982f  mov     [rsp+110h+var_D8], rax
0x180019834  xorps   xmm0, xmm0
0x180019837  movdqu  [rsp+110h+var_C0], xmm0
0x18001983d  xor     r12d, r12d
0x180019840  mov     [rbp+37h+var_B0], r12
0x180019844  test    r14, r14
0x180019847  jz      short loc_180019862
0x180019849  mov     [rsp+110h+var_E0], r14
0x18001984e  lea     rdx, [rsp+110h+var_E0]
0x180019853  lea     rcx, [rsp+110h+var_C8]
0x180019858  call    ?push_back@?$vector@PEAVCXdsReferenceInput@@V?$allocator@PEAVCXdsReferenceInput@@@std@@@std@@QEAAXAEBQEAVCXdsReferenceInput@@@Z; std::vector<CXdsReferenceInput *>::push_back(CXdsReferenceInput * const &)
0x18001985d  mov     [rsp+110h+var_D0], r12
0x180019862  test    rbx, rbx
0x180019865  jz      short loc_180019880
0x180019867  mov     [rsp+110h+var_E0], rbx
0x18001986c  lea     rdx, [rsp+110h+var_E0]
0x180019871  lea     rcx, [rsp+110h+var_C8]
0x180019876  call    ?push_back@?$vector@PEAVCXdsReferenceInput@@V?$allocator@PEAVCXdsReferenceInput@@@std@@@std@@QEAAXAEBQEAVCXdsReferenceInput@@@Z; std::vector<CXdsReferenceInput *>::push_back(CXdsReferenceInput * const &)
0x18001987b  mov     [rsp+110h+var_D8], r12
0x180019880  xor     ecx, ecx; char *
0x180019882  call    ?newstr@@YAPEADPEBD@Z; newstr(char const *)
0x180019887  mov     [rbp+37h+var_90], rax
0x18001988b  lea     rax, [rbp+37h+var_88]
0x18001988f  mov     [rsp+110h+var_E0], rax
0x180019894  xor     ecx, ecx; char *
0x180019896  call    ?newstr@@YAPEADPEBD@Z; newstr(char const *)
0x18001989b  mov     [rbp+37h+var_88], rax
0x18001989f  mov     [rbp+37h+var_80], 8004h
0x1800198a6  mov     rax, cs:off_180032978; "http://www.w3.org/2000/02/xmldsig#dsa"
0x1800198ad  mov     [rbp+37h+var_78], rax
0x1800198b1  lea     rdx, [rsp+110h+var_C8]
0x1800198b6  lea     rcx, [rbp+37h+var_70]
0x1800198ba  call    ??0?$vector@PEAVCXdsReferenceInput@@V?$allocator@PEAVCXdsReferenceInput@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<CXdsReferenceInput *>::vector<CXdsReferenceInput *>(std::vector<CXdsReferenceInput *> const &)
0x1800198bf  nop
0x1800198c0  mov     [rbp+37h+var_50], r12
0x1800198c4  xor     ecx, ecx; char *
0x1800198c6  call    ?newstr@@YAPEADPEBD@Z; newstr(char const *)
0x1800198cb  mov     [rbp+37h+var_48], rax
0x1800198cf  mov     eax, [rbp+37h+arg_38]
0x1800198d2  mov     [rbp+37h+var_40], eax
0x1800198d5  mov     [rbp+37h+var_38], r15
0x1800198d9  lea     rcx, [rbp+37h+var_90]; this
0x1800198dd  call    ?SignatureElement@CXdsSignature@@QEAAPEADXZ; CXdsSignature::SignatureElement(void)
0x1800198e2  mov     rcx, [rbp+37h+arg_40]
0x1800198e9  mov     [rcx], rax
0x1800198ec  lea     rcx, [rbp+37h+var_90]; this
0x1800198f0  call    ??1CXdsSignature@@QEAA@XZ; CXdsSignature::~CXdsSignature(void)
0x1800198f5  nop
0x1800198f6  lea     rcx, [rsp+110h+var_C8]
0x1800198fb  call    ?_Tidy@?$vector@PEAVCXdsReferenceInput@@V?$allocator@PEAVCXdsReferenceInput@@@std@@@std@@IEAAXXZ; std::vector<CXdsReferenceInput *>::_Tidy(void)
0x180019900  nop
0x180019901  lea     rcx, [rsp+110h+var_D8]
0x180019906  call    ??1?$P@VCXdsReferenceInput@@@@QEAA@XZ; P<CXdsReferenceInput>::~P<CXdsReferenceInput>(void)
0x18001990b  nop
0x18001990c  mov     rcx, rdi; Block
0x18001990f  call    cs:__imp_free
0x180019915  nop
0x180019916  lea     rcx, [rsp+110h+var_D0]
0x18001991b  call    ??1?$P@VCXdsReferenceInput@@@@QEAA@XZ; P<CXdsReferenceInput>::~P<CXdsReferenceInput>(void)
0x180019920  nop
0x180019921  mov     rcx, rsi; Block
0x180019924  call    cs:__imp_free
0x18001992a  nop
0x18001992b  xor     eax, eax
0x18001992d  add     rsp, 0E0h
0x180019934  pop     r15
0x180019936  pop     r14
0x180019938  pop     r12
0x18001993a  pop     rdi
0x18001993b  pop     rsi
0x18001993c  pop     rbx
0x18001993d  pop     rbp
0x18001993e  retn
```
