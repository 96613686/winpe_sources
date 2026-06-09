# KerbInitAsn(ASN1encoding_s * *,ASN1decoding_s * *)

- ea: `0x1800138c0`
- end: `0x1800139d5`
- name: `?KerbInitAsn@@YAJPEAPEAUASN1encoding_s@@PEAPEAUASN1decoding_s@@@Z`
- size: `277`
- prototype: `__int64 __fastcall(struct ASN1encoding_s **, struct ASN1decoding_s **)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002cbc`
- `0x18001a1d0`
- `0x18001b990`
- `0x18001cc90`

## callees

- `0x1800138c0`
- `0x180023ce0`

## import_xrefs

- `MSASN1!ASN1_CreateEncoder` at `0x180013928`
- `MSASN1!ASN1_CreateEncoder` at `0x180013928`
- `MSASN1!ASN1_CreateDecoder` at `0x180013901`
- `MSASN1!ASN1_CreateDecoder` at `0x180013901`
- `MSASN1!ASN1_CreateModule` at `0x180013988`
- `MSASN1!ASN1_CreateModule` at `0x180013988`

## pseudocode

```c
__int64 __fastcall KerbInitAsn(struct ASN1encoding_s **a1, struct ASN1decoding_s **a2)
{
  __int64 Module; // rax
  unsigned int Encoder; // eax

  if ( fKRB5ModuleStarted )
  {
    Module = PKU2UMSG_Module;
  }
  else
  {
    fKRB5ModuleStarted = 1;
    Module = ASN1_CreateModule(
               0x10000,
               1024,
               4096,
               49,
               off_180047350,
               off_1800471C0,
               off_180047030,
               qword_180049F80,
               846556016);
    PKU2UMSG_Module = Module;
  }
  if ( a1 )
    Encoder = ASN1_CreateEncoder(Module, a1, 0, 0, 0);
  else
    Encoder = ASN1_CreateDecoder(Module, a2, 0, 0, 0);
  if ( !Encoder )
    return 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids, Encoder);
  return 60;
}

```

## disassembly

```asm
0x1800138c0  sub     rsp, 58h
0x1800138c4  cmp     cs:?fKRB5ModuleStarted@@3HA, 0; int fKRB5ModuleStarted
0x1800138cb  mov     [rsp+58h+arg_8], rsi
0x1800138d0  mov     rsi, rdx
0x1800138d3  mov     [rsp+58h+var_8], rdi
0x1800138d8  mov     rdi, rcx
0x1800138db  jz      short loc_180013930
0x1800138dd  mov     rax, cs:PKU2UMSG_Module
0x1800138e4  mov     [rsp+58h+arg_0], rbx
0x1800138e9  xor     r9d, r9d
0x1800138ec  xor     ebx, ebx
0x1800138ee  xor     r8d, r8d
0x1800138f1  mov     [rsp+58h+var_38], rbx
0x1800138f6  mov     rcx, rax
0x1800138f9  test    rdi, rdi
0x1800138fc  jnz     short loc_180013925
0x1800138fe  mov     rdx, rsi
0x180013901  call    cs:__imp_ASN1_CreateDecoder
0x180013907  mov     rdi, [rsp+58h+var_8]
0x18001390c  mov     rsi, [rsp+58h+arg_8]
0x180013911  test    eax, eax
0x180013913  jnz     loc_18001399A
0x180013919  mov     eax, ebx
0x18001391b  mov     rbx, [rsp+58h+arg_0]
0x180013920  add     rsp, 58h
0x180013924  retn
0x180013925  mov     rdx, rdi
0x180013928  call    cs:__imp_ASN1_CreateEncoder
0x18001392e  jmp     short loc_180013907
0x180013930  mov     [rsp+58h+var_18], 32756B70h
0x180013938  lea     rax, qword_180049F80
0x18001393f  mov     [rsp+58h+var_20], rax
0x180013944  mov     edx, 400h
0x180013949  lea     rax, off_180047030
0x180013950  mov     cs:?fKRB5ModuleStarted@@3HA, 1; int fKRB5ModuleStarted
0x18001395a  mov     [rsp+58h+var_28], rax
0x18001395f  mov     r9d, 31h ; '1'
0x180013965  lea     rax, off_1800471C0
0x18001396c  mov     r8d, 1000h
0x180013972  mov     [rsp+58h+var_30], rax
0x180013977  mov     ecx, 10000h
0x18001397c  lea     rax, off_180047350
0x180013983  mov     [rsp+58h+var_38], rax
0x180013988  call    cs:__imp_ASN1_CreateModule
0x18001398e  mov     cs:PKU2UMSG_Module, rax
0x180013995  jmp     loc_1800138E4
0x18001399a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800139a1  lea     rdx, WPP_GLOBAL_Control
0x1800139a8  cmp     rcx, rdx
0x1800139ab  jz      short loc_1800139CB
0x1800139ad  test    byte ptr [rcx+1Ch], 1
0x1800139b1  jz      short loc_1800139CB
0x1800139b3  mov     rcx, [rcx+10h]
0x1800139b7  lea     r8, WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids
0x1800139be  mov     edx, 4Dh ; 'M'
0x1800139c3  mov     r9d, eax
0x1800139c6  call    WPP_SF_d
0x1800139cb  mov     eax, 3Ch ; '<'
0x1800139d0  jmp     loc_18001391B
```
