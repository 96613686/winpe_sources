# CDevice::ETWWriteResource(unsigned __int64,_EVENT_DESCRIPTOR const *,IDXGIResourceInternal *,IDXGISurface *,uint,bool)

- ea: `0x180033914`
- end: `0x180033bdb`
- name: `?ETWWriteResource@CDevice@@QEBAX_KPEBU_EVENT_DESCRIPTOR@@PEAUIDXGIResourceInternal@@PEAUIDXGISurface@@I_N@Z`
- size: `711`
- prototype: `void __fastcall(CDevice *__hidden this, unsigned __int64, const struct _EVENT_DESCRIPTOR *, struct IDXGIResourceInternal *, struct IDXGISurface *, char, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180033254`

## callees

- `0x180033914`
- `0x180035430`
- `0x1800a22f0`
- `0x1800a9d20`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180033ba1`
- `ntdll!EtwEventWrite` at `0x180033ba1`

## pseudocode

```c
void __fastcall CDevice::ETWWriteResource(
        CDevice *this,
        __int64 a2,
        const struct _EVENT_DESCRIPTOR *a3,
        RTL_SRWLOCK *a4,
        struct IDXGISurface *a5,
        char a6,
        bool a7)
{
  RTL_SRWLOCK *v7; // rbx
  __int64 Ptr; // r8
  unsigned int Ptr_high; // ecx
  int Ptr_low; // [rsp+20h] [rbp-E0h] BYREF
  int v13; // [rsp+24h] [rbp-DCh] BYREF
  int v14; // [rsp+28h] [rbp-D8h] BYREF
  int v15; // [rsp+2Ch] [rbp-D4h] BYREF
  int v16; // [rsp+30h] [rbp-D0h] BYREF
  int v17; // [rsp+34h] [rbp-CCh] BYREF
  int v18; // [rsp+38h] [rbp-C8h] BYREF
  int v19; // [rsp+3Ch] [rbp-C4h] BYREF
  int v20; // [rsp+40h] [rbp-C0h] BYREF
  int v21; // [rsp+44h] [rbp-BCh] BYREF
  int v22; // [rsp+48h] [rbp-B8h] BYREF
  int v23; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v24; // [rsp+50h] [rbp-B0h] BYREF
  int v25; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v26; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v27; // [rsp+60h] [rbp-A0h] BYREF
  char *v28; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v29[40]; // [rsp+70h] [rbp-90h] BYREF

  v7 = a4 - 26;
  Ptr = (__int64)a4[-5].Ptr;
  v27 = Ptr;
  if ( (a2 & 2) != 0 )
    CPrivateDataImpl<ID3D11DeviceChild>::ETWReportName(a4 - 26, a2, Ptr);
  if ( a7 )
  {
    Ptr_high = HIDWORD(v7[35].Ptr);
    v29[0] = &v27;
    v29[2] = &a5;
    v29[4] = (char *)this + 1240;
    Ptr_low = SLOBYTE(v7[31].Ptr);
    v29[6] = &Ptr_low;
    v13 = SBYTE2(v7[31].Ptr);
    v29[8] = &v13;
    v14 = (int)v7[41].Ptr;
    v29[10] = &v14;
    v15 = HIDWORD(v7[41].Ptr);
    v29[12] = &v15;
    v16 = LOWORD(v7[42].Ptr);
    v29[14] = &v16;
    v17 = LOBYTE(v7[35].Ptr);
    v29[16] = &v17;
    v18 = WORD1(v7[42].Ptr);
    v29[18] = &v18;
    v19 = SWORD2(v7[32].Ptr);
    v29[20] = &v19;
    v20 = (int)v7[33].Ptr;
    v29[22] = &v20;
    v21 = HIDWORD(v7[33].Ptr);
    v29[24] = &v21;
    v22 = WORD2(v7[34].Ptr);
    v29[26] = &v22;
    v23 = WORD1(v7[34].Ptr) << 16;
    v29[28] = &v23;
    v29[30] = &v24;
    v25 = (int)v7[46].Ptr;
    v29[32] = &v25;
    v29[1] = 8;
    v29[3] = 8;
    v29[5] = 8;
    v29[7] = 4;
    v29[9] = 4;
    v29[11] = 4;
    v29[13] = 4;
    v29[15] = 4;
    v29[17] = 4;
    v29[19] = 4;
    v29[21] = 4;
    v29[23] = 4;
    v29[25] = 4;
    v29[27] = 4;
    v29[29] = 4;
    v24 = Ptr_high;
    v29[31] = 4;
    v29[33] = 4;
    v29[34] = &a6;
    v28 = (char *)&v7[56];
    v29[36] = &v28;
    v29[35] = 4;
    v29[37] = 8;
    v26 = APIMiscFlagsToDDIMiscFlags(Ptr_high);
    v29[39] = 4;
    v29[38] = &v26;
    EtwEventWrite(Direct3D11EtwProviderGuid_Context, a3, 20, v29);
  }
}

```

## disassembly

```asm
0x180033914  mov     [rsp-8+arg_0], rbx
0x180033919  mov     [rsp-8+arg_8], rsi
0x18003391e  push    rbp
0x18003391f  push    rdi
0x180033920  push    r14
0x180033922  lea     rbp, [rsp-0C0h]
0x18003392a  sub     rsp, 1C0h
0x180033931  mov     rax, cs:__security_cookie
0x180033938  xor     rax, rsp
0x18003393b  mov     [rbp+0D0h+var_20], rax
0x180033942  lea     rbx, [r9-0D0h]
0x180033949  mov     rsi, r8
0x18003394c  mov     r8, [rbx+0A8h]
0x180033953  mov     rdi, rcx
0x180033956  mov     [rsp+1D0h+var_170], r8
0x18003395b  test    dl, 2
0x18003395e  jnz     loc_180033BCE
0x180033964  xor     r14d, r14d
0x180033967  cmp     [rbp+0D0h+arg_30], r14b
0x18003396e  jz      loc_180033BA7
0x180033974  mov     ecx, [rbx+11Ch]; unsigned int
0x18003397a  lea     rax, [rsp+1D0h+var_170]
0x18003397f  mov     [rsp+1D0h+var_160], rax
0x180033984  lea     rax, [rbp+0D0h+arg_20]
0x18003398b  mov     [rbp+0D0h+var_150], rax
0x18003398f  lea     rax, [rdi+4D8h]
0x180033996  mov     [rbp+0D0h+var_140], rax
0x18003399a  movsx   eax, byte ptr [rbx+0F8h]
0x1800339a1  mov     [rsp+1D0h+var_1B0], eax
0x1800339a5  lea     rax, [rsp+1D0h+var_1B0]
0x1800339aa  mov     [rbp+0D0h+var_130], rax
0x1800339ae  movsx   eax, byte ptr [rbx+0FAh]
0x1800339b5  mov     [rsp+1D0h+var_1AC], eax
0x1800339b9  lea     rax, [rsp+1D0h+var_1AC]
0x1800339be  mov     [rbp+0D0h+var_120], rax
0x1800339c2  mov     eax, [rbx+148h]
0x1800339c8  mov     [rsp+1D0h+var_1A8], eax
0x1800339cc  lea     rax, [rsp+1D0h+var_1A8]
0x1800339d1  mov     [rbp+0D0h+var_110], rax
0x1800339d5  mov     eax, [rbx+14Ch]
0x1800339db  mov     [rsp+1D0h+var_1A4], eax
0x1800339df  lea     rax, [rsp+1D0h+var_1A4]
0x1800339e4  mov     [rbp+0D0h+var_100], rax
0x1800339e8  movzx   eax, word ptr [rbx+150h]
0x1800339ef  mov     [rsp+1D0h+var_1A0], eax
0x1800339f3  lea     rax, [rsp+1D0h+var_1A0]
0x1800339f8  mov     [rbp+0D0h+var_F0], rax
0x1800339fc  movzx   eax, byte ptr [rbx+118h]
0x180033a03  mov     [rsp+1D0h+var_19C], eax
0x180033a07  lea     rax, [rsp+1D0h+var_19C]
0x180033a0c  mov     [rbp+0D0h+var_E0], rax
0x180033a10  movzx   eax, word ptr [rbx+152h]
0x180033a17  mov     [rsp+1D0h+var_198], eax
0x180033a1b  lea     rax, [rsp+1D0h+var_198]
0x180033a20  mov     [rbp+0D0h+var_D0], rax
0x180033a24  movsx   eax, word ptr [rbx+104h]
0x180033a2b  mov     [rsp+1D0h+var_194], eax
0x180033a2f  lea     rax, [rsp+1D0h+var_194]
0x180033a34  mov     [rbp+0D0h+var_C0], rax
0x180033a38  mov     eax, [rbx+108h]
0x180033a3e  mov     [rsp+1D0h+var_190], eax
0x180033a42  lea     rax, [rsp+1D0h+var_190]
0x180033a47  mov     [rbp+0D0h+var_B0], rax
0x180033a4b  mov     eax, [rbx+10Ch]
0x180033a51  mov     [rsp+1D0h+var_18C], eax
0x180033a55  lea     rax, [rsp+1D0h+var_18C]
0x180033a5a  mov     [rbp+0D0h+var_A0], rax
0x180033a5e  movzx   eax, word ptr [rbx+114h]
0x180033a65  mov     [rsp+1D0h+var_188], eax
0x180033a69  lea     rax, [rsp+1D0h+var_188]
0x180033a6e  mov     [rbp+0D0h+var_90], rax
0x180033a72  movzx   eax, word ptr [rbx+112h]
0x180033a79  shl     eax, 10h
0x180033a7c  mov     [rsp+1D0h+var_184], eax
0x180033a80  lea     rax, [rsp+1D0h+var_184]
0x180033a85  mov     [rbp+0D0h+var_80], rax
0x180033a89  lea     rax, [rsp+1D0h+var_180]
0x180033a8e  mov     [rbp+0D0h+var_70], rax
0x180033a92  mov     eax, [rbx+170h]
0x180033a98  mov     [rsp+1D0h+var_17C], eax
0x180033a9c  lea     rax, [rsp+1D0h+var_17C]
0x180033aa1  mov     [rbp+0D0h+var_60], rax
0x180033aa5  lea     rax, [rbp+0D0h+arg_28]
0x180033aac  mov     [rsp+1D0h+var_158], 8
0x180033ab5  mov     [rbp+0D0h+var_148], 8
0x180033abd  mov     [rbp+0D0h+var_138], 8
0x180033ac5  mov     [rbp+0D0h+var_128], 4
0x180033acd  mov     [rbp+0D0h+var_118], 4
0x180033ad5  mov     [rbp+0D0h+var_108], 4
0x180033add  mov     [rbp+0D0h+var_F8], 4
0x180033ae5  mov     [rbp+0D0h+var_E8], 4
0x180033aed  mov     [rbp+0D0h+var_D8], 4
0x180033af5  mov     [rbp+0D0h+var_C8], 4
0x180033afd  mov     [rbp+0D0h+var_B8], 4
0x180033b05  mov     [rbp+0D0h+var_A8], 4
0x180033b0d  mov     [rbp+0D0h+var_98], 4
0x180033b15  mov     [rbp+0D0h+var_88], 4
0x180033b1d  mov     [rbp+0D0h+var_78], 4
0x180033b25  mov     [rsp+1D0h+var_180], ecx
0x180033b29  mov     [rbp+0D0h+var_68], 4
0x180033b31  mov     [rbp+0D0h+var_58], 4
0x180033b39  mov     [rbp+0D0h+var_50], rax
0x180033b40  lea     rax, [rbx+1C0h]
0x180033b47  mov     [rsp+1D0h+var_168], rax
0x180033b4c  lea     rax, [rsp+1D0h+var_168]
0x180033b51  mov     [rbp+0D0h+var_40], rax
0x180033b58  mov     [rbp+0D0h+var_48], 4
0x180033b63  mov     [rbp+0D0h+var_38], 8
0x180033b6e  call    ?APIMiscFlagsToDDIMiscFlags@@YAII@Z; APIMiscFlagsToDDIMiscFlags(uint)
0x180033b73  mov     rcx, cs:Direct3D11EtwProviderGuid_Context
0x180033b7a  lea     r9, [rsp+1D0h+var_160]
0x180033b7f  mov     [rsp+1D0h+var_178], eax
0x180033b83  lea     r8d, [r14+14h]
0x180033b87  lea     rax, [rsp+1D0h+var_178]
0x180033b8c  mov     [rbp+0D0h+var_28], 4
0x180033b97  mov     rdx, rsi
0x180033b9a  mov     [rbp+0D0h+var_30], rax
0x180033ba1  call    cs:__imp_EtwEventWrite
0x180033ba7  mov     rcx, [rbp+0D0h+var_20]
0x180033bae  xor     rcx, rsp; StackCookie
0x180033bb1  call    __security_check_cookie
0x180033bb6  lea     r11, [rsp+1D0h+var_10]
0x180033bbe  mov     rbx, [r11+20h]
0x180033bc2  mov     rsi, [r11+28h]
0x180033bc6  mov     rsp, r11
0x180033bc9  pop     r14
0x180033bcb  pop     rdi
0x180033bcc  pop     rbp
0x180033bcd  retn
0x180033bce  mov     rcx, rbx
0x180033bd1  call    ?ETWReportName@?$CPrivateDataImpl@UID3D11DeviceChild@@@@QEAAXPEBU_EVENT_DESCRIPTOR@@PEBX@Z; CPrivateDataImpl<ID3D11DeviceChild>::ETWReportName(_EVENT_DESCRIPTOR const *,void const *)
0x180033bd6  jmp     loc_180033964
```
