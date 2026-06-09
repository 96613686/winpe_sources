# DrSerialPort::CreateSerialPort(tagRDPDR_DEVICE_ANNOUNCE *)

- ea: `0x14001dd70`
- end: `0x14001df51`
- name: `?CreateSerialPort@DrSerialPort@@AEAAJPEAUtagRDPDR_DEVICE_ANNOUNCE@@@Z`
- size: `481`
- prototype: `__int64 __fastcall(CHAR *this, struct tagRDPDR_DEVICE_ANNOUNCE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x14001df60`

## callees

- `0x140001e30`
- `0x1400027b0`
- `0x140003188`
- `0x14000324c`
- `0x140006480`
- `0x14001dd70`
- `0x14001e694`

## import_xrefs

- `ntoskrnl!RtlMultiByteToUnicodeN` at `0x14001ddcf`
- `ntoskrnl!RtlMultiByteToUnicodeN` at `0x14001ddcf`
- `ntoskrnl!RtlWriteRegistryValue` at `0x14001deed`
- `ntoskrnl!RtlWriteRegistryValue` at `0x14001deed`

## string_xrefs

- `0x14001ded6`: `SERIALCOMM`

## pseudocode

```c
__int64 __fastcall DrSerialPort::CreateSerialPort(CHAR *this, struct tagRDPDR_DEVICE_ANNOUNCE *a2)
{
  const CHAR *v4; // r9
  __int64 BytesInMultiByteString; // rax
  unsigned __int16 v6; // si
  unsigned int PortAnnounceEvent; // ebx
  struct tagRDPDR_PORTDEVICE_SUB *v8; // rdi
  unsigned int v10[2]; // [rsp+30h] [rbp-20h] BYREF
  WCHAR UnicodeString[8]; // [rsp+38h] [rbp-18h] BYREF

  v10[1] = 0;
  *(_OWORD *)UnicodeString = 0;
  v10[0] = 0;
  v4 = this + 48;
  BytesInMultiByteString = -1;
  do
    ++BytesInMultiByteString;
  while ( v4[BytesInMultiByteString] );
  if ( RtlMultiByteToUnicodeN(UnicodeString, 0x10u, &v10[1], v4, BytesInMultiByteString) < 0
    || (v6 = v10[1], v10[1] > 0xE) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_44ce53adbdd53bd53a5d7d28e4f35355_Traceguids);
    return 3221225473LL;
  }
  else
  {
    UnicodeString[(unsigned __int64)v10[1] >> 1] = 0;
    PortAnnounceEvent = DrPrinterPort::CreatePortAnnounceEvent((DrPrinterPort *)this, a2, 0, 0, &qword_140008DC8, v10);
    if ( PortAnnounceEvent == -1073741789 )
    {
      v8 = (struct tagRDPDR_PORTDEVICE_SUB *)operator new(v10[0], 0x40u);
      if ( v8 )
      {
        PortAnnounceEvent = DrPrinterPort::CreatePortAnnounceEvent(
                              (DrPrinterPort *)this,
                              a2,
                              v8,
                              v10[0],
                              UnicodeString,
                              0);
        if ( PortAnnounceEvent )
        {
          operator delete(v8);
        }
        else
        {
          PortAnnounceEvent = RDPDYN_DispatchNewDevMgmtEvent(v8, *(_DWORD *)(*((_QWORD *)this + 4) + 1128LL), 4u, 0);
          RtlWriteRegistryValue(4u, L"SERIALCOMM", UnicodeString, 1u, UnicodeString, v6 + 2);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_44ce53adbdd53bd53a5d7d28e4f35355_Traceguids);
        return (unsigned int)-1073741801;
      }
    }
    return PortAnnounceEvent;
  }
}

```

## disassembly

```asm
0x14001dd70  mov     [rsp-28h+arg_10], rbx
0x14001dd75  push    rbp
0x14001dd76  push    rsi
0x14001dd77  push    rdi
0x14001dd78  push    r14
0x14001dd7a  push    r15
0x14001dd7c  mov     rbp, rsp
0x14001dd7f  sub     rsp, 50h
0x14001dd83  mov     rax, cs:__security_cookie
0x14001dd8a  xor     rax, rsp
0x14001dd8d  mov     [rbp+var_8], rax
0x14001dd91  xorps   xmm0, xmm0
0x14001dd94  mov     [rbp+var_20+4], 0
0x14001dd9b  movups  xmmword ptr [rbp+UnicodeString], xmm0
0x14001dd9f  mov     r15, rdx
0x14001dda2  mov     [rbp+var_20], 0
0x14001dda9  mov     r14, rcx
0x14001ddac  lea     r9, [rcx+30h]; MultiByteString
0x14001ddb0  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001ddb4  inc     rax
0x14001ddb7  cmp     byte ptr [r9+rax], 0
0x14001ddbc  jnz     short loc_14001DDB4
0x14001ddbe  lea     r8, [rbp+var_20+4]; BytesInUnicodeString
0x14001ddc2  mov     [rsp+50h+BytesInMultiByteString], eax; BytesInMultiByteString
0x14001ddc6  mov     edx, 10h; MaxBytesInUnicodeString
0x14001ddcb  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x14001ddcf  call    cs:__imp_RtlMultiByteToUnicodeN
0x14001ddd6  nop     dword ptr [rax+rax+00h]
0x14001dddb  test    eax, eax
0x14001dddd  js      loc_14001DEFD
0x14001dde3  mov     esi, [rbp+var_20+4]
0x14001dde6  cmp     esi, 0Eh
0x14001dde9  ja      loc_14001DEFD
0x14001ddef  xor     eax, eax
0x14001ddf1  mov     ecx, esi
0x14001ddf3  shr     rcx, 1
0x14001ddf6  xor     r9d, r9d; unsigned int
0x14001ddf9  xor     r8d, r8d; struct tagRDPDR_PORTDEVICE_SUB *
0x14001ddfc  mov     rdx, r15; struct tagRDPDR_DEVICE_ANNOUNCE *
0x14001ddff  mov     [rbp+rcx*2+UnicodeString], ax
0x14001de04  lea     rax, [rbp+var_20]
0x14001de08  mov     qword ptr [rsp+50h+ValueLength], rax; unsigned int *
0x14001de0d  mov     rcx, r14; this
0x14001de10  lea     rax, qword_140008DC8
0x14001de17  mov     qword ptr [rsp+50h+BytesInMultiByteString], rax; unsigned __int16 *
0x14001de1c  call    ?CreatePortAnnounceEvent@DrPrinterPort@@QEAAJPEAUtagRDPDR_DEVICE_ANNOUNCE@@PEAUtagRDPDR_PORTDEVICE_SUB@@KPEBGPEAK@Z; DrPrinterPort::CreatePortAnnounceEvent(tagRDPDR_DEVICE_ANNOUNCE *,tagRDPDR_PORTDEVICE_SUB *,ulong,ushort const *,ulong *)
0x14001de21  mov     ebx, eax
0x14001de23  cmp     eax, 0C0000023h
0x14001de28  jnz     loc_14001DEF9
0x14001de2e  mov     ecx, [rbp+var_20]; unsigned __int64
0x14001de31  mov     edx, 40h ; '@'; unsigned __int64
0x14001de36  call    ??2@YAPEAX_K0@Z; operator new(unsigned __int64,unsigned __int64)
0x14001de3b  mov     rdi, rax
0x14001de3e  test    rax, rax
0x14001de41  jnz     short loc_14001DE79
0x14001de43  mov     rcx, cs:WPP_GLOBAL_Control
0x14001de4a  lea     rax, WPP_GLOBAL_Control
0x14001de51  cmp     rcx, rax
0x14001de54  jz      short loc_14001DE6F
0x14001de56  cmp     byte ptr [rcx+29h], 2
0x14001de5a  jb      short loc_14001DE6F
0x14001de5c  mov     rcx, [rcx+18h]
0x14001de60  lea     edx, [rdi+0Bh]
0x14001de63  lea     r8, WPP_44ce53adbdd53bd53a5d7d28e4f35355_Traceguids
0x14001de6a  call    WPP_SF_
0x14001de6f  mov     ebx, 0C0000017h
0x14001de74  jmp     loc_14001DEF9
0x14001de79  mov     r9d, [rbp+var_20]; unsigned int
0x14001de7d  lea     rax, [rbp+UnicodeString]
0x14001de81  mov     qword ptr [rsp+50h+ValueLength], 0; unsigned int *
0x14001de8a  mov     r8, rdi; struct tagRDPDR_PORTDEVICE_SUB *
0x14001de8d  mov     rdx, r15; struct tagRDPDR_DEVICE_ANNOUNCE *
0x14001de90  mov     qword ptr [rsp+50h+BytesInMultiByteString], rax; unsigned __int16 *
0x14001de95  mov     rcx, r14; this
0x14001de98  call    ?CreatePortAnnounceEvent@DrPrinterPort@@QEAAJPEAUtagRDPDR_DEVICE_ANNOUNCE@@PEAUtagRDPDR_PORTDEVICE_SUB@@KPEBGPEAK@Z; DrPrinterPort::CreatePortAnnounceEvent(tagRDPDR_DEVICE_ANNOUNCE *,tagRDPDR_PORTDEVICE_SUB *,ulong,ushort const *,ulong *)
0x14001de9d  mov     ebx, eax
0x14001de9f  mov     rcx, rdi; void *
0x14001dea2  test    eax, eax
0x14001dea4  jz      short loc_14001DEAD
0x14001dea6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14001deab  jmp     short loc_14001DEF9
0x14001dead  mov     rdx, [r14+20h]
0x14001deb1  xor     r9d, r9d; struct DrDevice *
0x14001deb4  mov     edx, [rdx+468h]; unsigned int
0x14001deba  lea     r14d, [r9+4]
0x14001debe  mov     r8d, r14d; unsigned int
0x14001dec1  call    RDPDYN_DispatchNewDevMgmtEvent
0x14001dec6  mov     ebx, eax
0x14001dec8  lea     r9d, [r14-3]; ValueType
0x14001decc  movzx   eax, si
0x14001decf  lea     r8, [rbp+UnicodeString]; ValueName
0x14001ded3  add     eax, 2
0x14001ded6  lea     rdx, Path; "SERIALCOMM"
0x14001dedd  mov     [rsp+50h+ValueLength], eax; ValueLength
0x14001dee1  mov     ecx, r14d; RelativeTo
0x14001dee4  lea     rax, [rbp+UnicodeString]
0x14001dee8  mov     qword ptr [rsp+50h+BytesInMultiByteString], rax; ValueData
0x14001deed  call    cs:__imp_RtlWriteRegistryValue
0x14001def4  nop     dword ptr [rax+rax+00h]
0x14001def9  mov     eax, ebx
0x14001defb  jmp     short loc_14001DF30
0x14001defd  mov     rcx, cs:WPP_GLOBAL_Control
0x14001df04  lea     rax, WPP_GLOBAL_Control
0x14001df0b  cmp     rcx, rax
0x14001df0e  jz      short loc_14001DF2B
0x14001df10  cmp     byte ptr [rcx+29h], 2
0x14001df14  jb      short loc_14001DF2B
0x14001df16  mov     rcx, [rcx+18h]
0x14001df1a  lea     r8, WPP_44ce53adbdd53bd53a5d7d28e4f35355_Traceguids
0x14001df21  mov     edx, 0Ah
0x14001df26  call    WPP_SF_
0x14001df2b  mov     eax, 0C0000001h
0x14001df30  mov     rcx, [rbp+var_8]
0x14001df34  xor     rcx, rsp; StackCookie
0x14001df37  call    __security_check_cookie
0x14001df3c  mov     rbx, [rsp+50h+arg_10]
0x14001df44  add     rsp, 50h
0x14001df48  pop     r15
0x14001df4a  pop     r14
0x14001df4c  pop     rdi
0x14001df4d  pop     rsi
0x14001df4e  pop     rbp
0x14001df4f  retn
```
