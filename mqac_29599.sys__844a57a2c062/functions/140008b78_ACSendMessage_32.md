# ACSendMessage_32

- ea: `0x140008b78`
- end: `0x140008d38`
- name: `ACSendMessage_32`
- size: `448`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, volatile void *Address)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x14000a3b0`

## callees

- `0x1400010a4`
- `0x140001710`
- `0x140001a04`
- `0x140003d84`
- `0x14000881c`
- `0x140008b78`
- `0x140024bb0`
- `0x140024fc0`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140008c20`
- `ntoskrnl!ProbeForRead` at `0x140008c20`

## pseudocode

```c
__int64 __fastcall ACSendMessage_32(
        struct _DEVICE_OBJECT *a1,
        __int64 a2,
        int a3,
        const struct CQueueBase *a4,
        volatile void *Address)
{
  __int64 result; // rax
  _DWORD *DeviceExtension; // rbx
  unsigned int v11; // esi
  const struct CACMessageProperties64Helper *v12; // rdx
  _QWORD v13[22]; // [rsp+40h] [rbp-3B8h] BYREF
  void *v14[88]; // [rsp+F0h] [rbp-308h] BYREF

  memset(v14, 0, sizeof(v14));
  memset(v13, 0, 168);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 74, &WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, a4);
  }
  ProbeForRead(Address, 0x16Cu, 1u);
  result = ACpSendParams32ToSendParams(
             (const struct CACSendParameters_32 *)Address,
             (struct CACSendParameters64Helper *)v13,
             (struct CACSendParameters *)v14);
  if ( (int)result >= 0 )
  {
    DeviceExtension = a1->DeviceExtension;
    DeviceExtension[246] = 1;
    v11 = ACSendMessage(a1, a2, a3, a4, (struct CACSendParameters *)v14);
    DeviceExtension[246] = 0;
    ACpMsgPropsToMsgProps32((const struct CACMessageProperties *)v14, v12, (struct CACMessageProperties_32 *)Address);
    if ( LODWORD(v14[74]) )
    {
      operator delete(v14[73]);
      v14[73] = 0;
    }
    if ( LODWORD(v14[76]) )
    {
      operator delete(v14[75]);
      v14[75] = 0;
    }
    *((_DWORD *)Address + 79) = v14[78];
    return v11;
  }
  return result;
}

```

## disassembly

```asm
0x140008b78  push    rbx
0x140008b7a  push    rsi
0x140008b7b  push    rdi
0x140008b7c  push    r12
0x140008b7e  push    r14
0x140008b80  push    r15
0x140008b82  sub     rsp, 3C8h
0x140008b89  mov     rax, cs:__security_cookie
0x140008b90  xor     rax, rsp
0x140008b93  mov     [rsp+3F8h+var_48], rax
0x140008b9b  mov     rsi, r9
0x140008b9e  mov     r12d, r8d
0x140008ba1  mov     r15, rdx
0x140008ba4  mov     r14, rcx
0x140008ba7  mov     rdi, [rsp+3F8h+Address]
0x140008baf  xor     edx, edx; Val
0x140008bb1  mov     r8d, 2C0h; Size
0x140008bb7  lea     rcx, [rsp+3F8h+var_308]; void *
0x140008bbf  call    memset
0x140008bc4  mov     [rsp+3F8h+var_3B8], 0
0x140008bcd  xor     edx, edx; Val
0x140008bcf  mov     r8d, 0A0h; Size
0x140008bd5  lea     rcx, [rsp+3F8h+var_3B0]; void *
0x140008bda  call    memset
0x140008bdf  lea     rax, WPP_GLOBAL_Control
0x140008be6  mov     rcx, cs:WPP_GLOBAL_Control
0x140008bed  cmp     rcx, rax
0x140008bf0  jz      short loc_140008C12
0x140008bf2  mov     eax, [rcx+6Ch]
0x140008bf5  test    al, 4
0x140008bf7  jz      short loc_140008C12
0x140008bf9  mov     edx, 4Ah ; 'J'
0x140008bfe  mov     r9, rsi
0x140008c01  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140008c08  mov     rcx, [rcx+58h]
0x140008c0c  call    WPP_SF_q
0x140008c11  nop
0x140008c12  mov     edx, 16Ch; Length
0x140008c17  mov     r8d, 1; Alignment
0x140008c1d  mov     rcx, rdi; Address
0x140008c20  call    cs:__imp_ProbeForRead
0x140008c27  nop     dword ptr [rax+rax+00h]
0x140008c2c  lea     r8, [rsp+3F8h+var_308]; struct CACSendParameters *
0x140008c34  lea     rdx, [rsp+3F8h+var_3B8]; struct CACSendParameters64Helper *
0x140008c39  mov     rcx, rdi; struct CACSendParameters_32 *
0x140008c3c  call    ?ACpSendParams32ToSendParams@@YAJPEBVCACSendParameters_32@@PEAUCACSendParameters64Helper@@PEAVCACSendParameters@@@Z; ACpSendParams32ToSendParams(CACSendParameters_32 const *,CACSendParameters64Helper *,CACSendParameters *)
0x140008c41  mov     [rsp+3F8h+var_3C8], eax
0x140008c45  test    eax, eax
0x140008c47  js      loc_140008D16
0x140008c4d  mov     rbx, [r14+40h]
0x140008c51  mov     dword ptr [rbx+3D8h], 1
0x140008c5b  lea     rax, [rsp+3F8h+var_308]
0x140008c63  mov     [rsp+3F8h+var_3D8], rax
0x140008c68  mov     r9, rsi
0x140008c6b  mov     r8d, r12d
0x140008c6e  mov     rdx, r15
0x140008c71  mov     rcx, r14
0x140008c74  call    ACSendMessage
0x140008c79  mov     esi, eax
0x140008c7b  mov     dword ptr [rbx+3D8h], 0
0x140008c85  mov     r8, rdi; struct CACMessageProperties_32 *
0x140008c88  lea     rcx, [rsp+3F8h+var_308]; struct CACMessageProperties *
0x140008c90  call    ?ACpMsgPropsToMsgProps32@@YAXPEBVCACMessageProperties@@PEBUCACMessageProperties64Helper@@PEAVCACMessageProperties_32@@@Z; ACpMsgPropsToMsgProps32(CACMessageProperties const *,CACMessageProperties64Helper const *,CACMessageProperties_32 *)
0x140008c95  cmp     [rsp+3F8h+var_B8], 0
0x140008c9d  jz      short loc_140008CB8
0x140008c9f  mov     rcx, [rsp+3F8h+var_C0]; void *
0x140008ca7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140008cac  mov     [rsp+3F8h+var_C0], 0
0x140008cb8  cmp     [rsp+3F8h+var_A8], 0
0x140008cc0  jz      short loc_140008CDB
0x140008cc2  mov     rcx, [rsp+3F8h+var_B0]; void *
0x140008cca  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140008ccf  mov     [rsp+3F8h+var_B0], 0
0x140008cdb  mov     eax, [rsp+3F8h+var_98]
0x140008ce2  mov     [rdi+13Ch], eax
0x140008ce8  mov     eax, esi
0x140008cea  jmp     short loc_140008D16
0x140008cec  jmp     short loc_140008D16
0x140008cee  mov     ebx, eax
0x140008cf0  mov     rcx, [rsp+3F8h+var_C0]; void *
0x140008cf8  test    rcx, rcx
0x140008cfb  jz      short loc_140008D02
0x140008cfd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140008d02  mov     rcx, [rsp+3F8h+var_B0]; void *
0x140008d0a  test    rcx, rcx
0x140008d0d  jz      short loc_140008D14
0x140008d0f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140008d14  mov     eax, ebx
0x140008d16  mov     rcx, [rsp+3F8h+var_48]
0x140008d1e  xor     rcx, rsp; StackCookie
0x140008d21  call    __security_check_cookie
0x140008d26  add     rsp, 3C8h
0x140008d2d  pop     r15
0x140008d2f  pop     r14
0x140008d31  pop     r12
0x140008d33  pop     rdi
0x140008d34  pop     rsi
0x140008d35  pop     rbx
0x140008d36  retn
```
