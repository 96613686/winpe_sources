# FltpGetSupportedFeaturesValue

- ea: `0x18006aef0`
- end: `0x18006b0c7`
- name: `FltpGetSupportedFeaturesValue`
- size: `471`
- prototype: `__int64 __fastcall(__int64, const UNICODE_STRING *, __int64)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x1800509d0`
- `0x180054f50`
- `0x180069c90`

## callees

- `0x180009f20`
- `0x1800247a0`
- `0x18006aef0`
- `0x18006b0d0`
- `0x18006b1c0`
- `0x18006b2b0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18006af5c`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006af5c`
- `ntoskrnl!ZwClose` at `0x18006afc9`
- `ntoskrnl!ZwClose` at `0x18006b083`
- `ntoskrnl!ZwClose` at `0x18006afc9`
- `ntoskrnl!ZwClose` at `0x18006b083`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x18006af80`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x18006af80`

## pseudocode

```c
__int64 __fastcall FltpGetSupportedFeaturesValue(__int64 a1, const UNICODE_STRING *a2, __int64 a3)
{
  unsigned int v5; // edi
  int RegDwordValue; // esi
  int v9; // esi
  unsigned int v10; // [rsp+30h] [rbp-198h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-190h] BYREF
  _QWORD v12[2]; // [rsp+40h] [rbp-188h] BYREF
  UNICODE_STRING DestinationString; // [rsp+50h] [rbp-178h] BYREF
  char v14; // [rsp+60h] [rbp-168h] BYREF

  Handle = 0;
  v12[0] = 20971520;
  v5 = 0;
  v12[1] = &v14;
  v10 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"SupportedFeatures");
  RegDwordValue = IoOpenDriverRegistryKey(a1, 0, 131097, 0, &Handle);
  if ( (int)FltpDbgStatus(RegDwordValue) >= 0 )
  {
    RegDwordValue = FltpGetRegDwordValue(Handle, v12, &DestinationString, &v10);
    ZwClose(Handle);
    v5 = v10;
  }
  if ( (int)FltpDbgStatus(RegDwordValue) < 0 )
  {
    v9 = FltpOpenServiceRootRegistryKey(a1, &Handle);
    if ( (int)FltpDbgStatus(v9) >= 0 )
    {
      v9 = FltpGetRegDwordValue(Handle, v12, &DestinationString, &v10);
      ZwClose(Handle);
      v5 = v10;
    }
    if ( (int)FltpDbgStatus(v9) < 0 )
      v5 = 0;
  }
  if ( a2 )
    v5 |= FltpGetAutoOptInFeatures(a2);
  if ( a3 && (*(_DWORD *)(a3 + 96) & 0x80u) == 0 )
    v5 |= 8u;
  return v5;
}

```

## disassembly

```asm
0x18006aef0  mov     [rsp+arg_10], rbx
0x18006aef5  mov     [rsp+arg_18], rbp
0x18006aefa  push    rsi
0x18006aefb  push    rdi
0x18006aefc  push    r14
0x18006aefe  sub     rsp, 1B0h
0x18006af05  mov     rax, cs:__security_cookie
0x18006af0c  xor     rax, rsp
0x18006af0f  mov     [rsp+1C8h+var_28], rax
0x18006af17  xorps   xmm0, xmm0
0x18006af1a  mov     [rsp+1C8h+Handle], 0
0x18006af23  movups  [rsp+1C8h+var_188], xmm0
0x18006af28  mov     eax, 140h
0x18006af2d  mov     rbp, rdx
0x18006af30  mov     word ptr [rsp+1C8h+var_188+2], ax
0x18006af35  lea     rdx, aSupportedfeatu; "SupportedFeatures"
0x18006af3c  lea     rax, [rsp+1C8h+var_168]
0x18006af41  mov     r14, rcx
0x18006af44  xor     edi, edi
0x18006af46  mov     qword ptr [rsp+1C8h+var_188+8], rax
0x18006af4b  lea     rcx, [rsp+1C8h+DestinationString]; DestinationString
0x18006af50  mov     [rsp+1C8h+var_198], edi
0x18006af54  mov     rbx, r8
0x18006af57  movups  xmmword ptr [rsp+1C8h+DestinationString.Length], xmm0
0x18006af5c  call    cs:__imp_RtlInitUnicodeString
0x18006af63  nop     dword ptr [rax+rax+00h]
0x18006af68  lea     rax, [rsp+1C8h+Handle]
0x18006af6d  xor     r9d, r9d
0x18006af70  xor     edx, edx
0x18006af72  mov     [rsp+1C8h+var_1A8], rax
0x18006af77  mov     r8d, 20019h
0x18006af7d  mov     rcx, r14
0x18006af80  call    cs:__imp_IoOpenDriverRegistryKey
0x18006af87  nop     dword ptr [rax+rax+00h]
0x18006af8c  mov     r8d, 1463h
0x18006af92  lea     rdx, aMinkernelFsFil_29; "minkernel\\fs\\filtermgr\\filter\\enume"...
0x18006af99  mov     ecx, eax
0x18006af9b  xor     r9d, r9d
0x18006af9e  mov     esi, eax
0x18006afa0  call    FltpDbgStatus
0x18006afa5  test    eax, eax
0x18006afa7  js      short loc_18006AFD9
0x18006afa9  mov     rcx, [rsp+1C8h+Handle]
0x18006afae  lea     r9, [rsp+1C8h+var_198]
0x18006afb3  lea     r8, [rsp+1C8h+DestinationString]
0x18006afb8  lea     rdx, [rsp+1C8h+var_188]
0x18006afbd  call    FltpGetRegDwordValue
0x18006afc2  mov     rcx, [rsp+1C8h+Handle]; Handle
0x18006afc7  mov     esi, eax
0x18006afc9  call    cs:__imp_ZwClose
0x18006afd0  nop     dword ptr [rax+rax+00h]
0x18006afd5  mov     edi, [rsp+1C8h+var_198]
0x18006afd9  mov     r8d, 1476h
0x18006afdf  lea     rdx, aMinkernelFsFil_29; "minkernel\\fs\\filtermgr\\filter\\enume"...
0x18006afe6  xor     r9d, r9d
0x18006afe9  mov     ecx, esi
0x18006afeb  call    FltpDbgStatus
0x18006aff0  test    eax, eax
0x18006aff2  js      short loc_18006B039
0x18006aff4  test    rbp, rbp
0x18006aff7  jnz     loc_18006B0B8
0x18006affd  test    rbx, rbx
0x18006b000  jz      short loc_18006B009
0x18006b002  mov     ecx, [rbx+60h]
0x18006b005  test    cl, cl
0x18006b007  jns     short loc_18006B034
0x18006b009  mov     eax, edi
0x18006b00b  mov     rcx, [rsp+1C8h+var_28]
0x18006b013  xor     rcx, rsp; StackCookie
0x18006b016  call    __security_check_cookie
0x18006b01b  lea     r11, [rsp+1C8h+var_18]
0x18006b023  mov     rbx, [r11+30h]
0x18006b027  mov     rbp, [r11+38h]
0x18006b02b  mov     rsp, r11
0x18006b02e  pop     r14
0x18006b030  pop     rdi
0x18006b031  pop     rsi
0x18006b032  retn
0x18006b034  or      edi, 8
0x18006b037  jmp     short loc_18006B009
0x18006b039  lea     rdx, [rsp+1C8h+Handle]
0x18006b03e  mov     rcx, r14
0x18006b041  call    FltpOpenServiceRootRegistryKey
0x18006b046  mov     r8d, 147Ah
0x18006b04c  lea     rdx, aMinkernelFsFil_29; "minkernel\\fs\\filtermgr\\filter\\enume"...
0x18006b053  xor     r9d, r9d
0x18006b056  mov     ecx, eax
0x18006b058  mov     esi, eax
0x18006b05a  call    FltpDbgStatus
0x18006b05f  test    eax, eax
0x18006b061  js      short loc_18006B093
0x18006b063  mov     rcx, [rsp+1C8h+Handle]
0x18006b068  lea     r9, [rsp+1C8h+var_198]
0x18006b06d  lea     r8, [rsp+1C8h+DestinationString]
0x18006b072  lea     rdx, [rsp+1C8h+var_188]
0x18006b077  call    FltpGetRegDwordValue
0x18006b07c  mov     rcx, [rsp+1C8h+Handle]; Handle
0x18006b081  mov     esi, eax
0x18006b083  call    cs:__imp_ZwClose
0x18006b08a  nop     dword ptr [rax+rax+00h]
0x18006b08f  mov     edi, [rsp+1C8h+var_198]
0x18006b093  xor     r9d, r9d
0x18006b096  lea     rdx, aMinkernelFsFil_29; "minkernel\\fs\\filtermgr\\filter\\enume"...
0x18006b09d  mov     r8d, 1488h
0x18006b0a3  mov     ecx, esi
0x18006b0a5  call    FltpDbgStatus
0x18006b0aa  mov     edx, eax
0x18006b0ac  xor     eax, eax
0x18006b0ae  test    edx, edx
0x18006b0b0  cmovs   edi, eax
0x18006b0b3  jmp     loc_18006AFF4
0x18006b0b8  mov     rcx, rbp; Altitude2
0x18006b0bb  call    FltpGetAutoOptInFeatures
0x18006b0c0  or      edi, eax
0x18006b0c2  jmp     loc_18006AFFD
```
