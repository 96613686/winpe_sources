# CRecvFromPipe::GeneratePacketRadius(CPacketRadius * *,IAttributesRaw *)

- ea: `0x180016efc`
- end: `0x1800170bb`
- name: `?GeneratePacketRadius@CRecvFromPipe@@AEAAJPEAPEAVCPacketRadius@@PEAUIAttributesRaw@@@Z`
- size: `447`
- prototype: `__int64 __fastcall(CRecvFromPipe *__hidden this, struct CPacketRadius **, struct IAttributesRaw *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800179a4`

## callees

- `0x1800094e4`
- `0x18000e4e0`
- `0x180012764`
- `0x180016efc`
- `0x1800170c4`
- `0x18001d31c`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001709e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001709e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016f2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016f2e`

## string_xrefs

- `0x180017058`: `Unable to create a Packet-Radius object while generating an out-bound packet`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRecvFromPipe::GeneratePacketRadius(
        CRecvFromPipe *this,
        struct CPacketRadius **a2,
        struct IAttributesRaw *a3)
{
  unsigned __int8 *v6; // rax
  unsigned __int8 *v7; // rdi
  int OutPacketInfo; // ebx
  const struct std::nothrow_t *v9; // rdx
  struct CPacketRadius *v10; // rax
  struct IIasClient *v11; // rsi
  struct IIasClient *v13; // [rsp+60h] [rbp-28h] BYREF
  struct sockaddr *v14; // [rsp+68h] [rbp-20h] BYREF
  struct CPacketRadius *v15; // [rsp+A8h] [rbp+20h] BYREF

  v14 = 0;
  LOWORD(v15) = 0;
  v13 = 0;
  v6 = (unsigned __int8 *)CoTaskMemAlloc(0x14u);
  v7 = v6;
  if ( !v6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("Unable to allocate memory for packet header information while generating out-bound packet");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_ed9712b053c33f492fa08cace3005bc4_Traceguids, "NPSRAD");
    }
    return (unsigned int)-2147024882;
  }
  OutPacketInfo = CRecvFromPipe::GetOutPacketInfo(this, &v14, (unsigned __int16 *)&v15, &v13, v6, a3);
  if ( OutPacketInfo < 0 )
  {
LABEL_16:
    CoTaskMemFree(v7);
    return (unsigned int)OutPacketInfo;
  }
  v10 = (struct CPacketRadius *)operator new[](0xB0u, v9);
  v15 = v10;
  v11 = v13;
  if ( v10 )
    v10 = (struct CPacketRadius *)CPacketRadius::CPacketRadius(
                                    v10,
                                    *((_QWORD *)this + 3),
                                    *((_QWORD *)this + 4),
                                    v13,
                                    *((_QWORD *)this + 8),
                                    v7,
                                    20,
                                    v14,
                                    -1,
                                    1,
                                    *((_DWORD *)this + 2));
  *a2 = v10;
  if ( !v10 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("Unable to create a Packet-Radius object while generating an out-bound packet");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_ed9712b053c33f492fa08cace3005bc4_Traceguids, "NPSRAD");
    }
    (*(void (__fastcall **)(struct IIasClient *))(*(_QWORD *)v11 + 16LL))(v11);
    OutPacketInfo = -2147024882;
    goto LABEL_16;
  }
  return (unsigned int)OutPacketInfo;
}

```

## disassembly

```asm
0x180016efc  mov     r11, rsp
0x180016eff  mov     [r11+8], rbx
0x180016f03  mov     [r11+10h], rbp
0x180016f07  push    rsi
0x180016f08  push    rdi
0x180016f09  push    r14
0x180016f0b  sub     rsp, 70h
0x180016f0f  mov     rbx, r8
0x180016f12  mov     r14, rdx
0x180016f15  mov     rbp, rcx
0x180016f18  mov     qword ptr [r11-20h], 0
0x180016f20  xor     eax, eax
0x180016f22  mov     [r11+20h], ax
0x180016f27  mov     [r11-28h], rax
0x180016f2b  lea     ecx, [rax+14h]; cb
0x180016f2e  call    cs:__imp_CoTaskMemAlloc
0x180016f34  mov     rdi, rax
0x180016f37  test    rax, rax
0x180016f3a  jnz     short loc_180016F95
0x180016f3c  lea     rcx, WPP_GLOBAL_Control
0x180016f43  mov     rax, cs:WPP_GLOBAL_Control
0x180016f4a  cmp     rax, rcx
0x180016f4d  jz      short loc_180016F8B
0x180016f4f  cmp     byte ptr [rax+19h], 2
0x180016f53  jb      short loc_180016F8B
0x180016f55  test    dword ptr [rax+1Ch], 100h
0x180016f5c  jz      short loc_180016F8B
0x180016f5e  lea     rcx, aUnableToAlloca_6; "Unable to allocate memory for packet he"...
0x180016f65  call    WppDbgPrint
0x180016f6a  lea     edx, [rdi+1Eh]
0x180016f6d  lea     r9, aNpsrad; "NPSRAD"
0x180016f74  lea     r8, WPP_ed9712b053c33f492fa08cace3005bc4_Traceguids
0x180016f7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180016f82  mov     rcx, [rcx+10h]
0x180016f86  call    WPP_SF_s
0x180016f8b  mov     ebx, 8007000Eh
0x180016f90  jmp     loc_1800170A4
0x180016f95  mov     [rsp+88h+var_60], rbx; struct IAttributesRaw *
0x180016f9a  mov     [rsp+88h+var_68], rdi; unsigned __int8 *
0x180016f9f  lea     r9, [rsp+88h+var_28]; struct IIasClient **
0x180016fa4  lea     r8, [rsp+88h+arg_18]; unsigned __int16 *
0x180016fac  lea     rdx, [rsp+88h+var_20]; struct sockaddr **
0x180016fb1  mov     rcx, rbp; this
0x180016fb4  call    ?GetOutPacketInfo@CRecvFromPipe@@AEAAJPEAPEAUsockaddr@@PEAGPEAPEAUIIasClient@@PEAEPEAUIAttributesRaw@@@Z; CRecvFromPipe::GetOutPacketInfo(sockaddr * *,ushort *,IIasClient * *,uchar *,IAttributesRaw *)
0x180016fb9  mov     ebx, eax
0x180016fbb  test    eax, eax
0x180016fbd  js      loc_18001709B
0x180016fc3  mov     ecx, 0B0h; Size
0x180016fc8  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180016fcd  mov     r10, rax
0x180016fd0  mov     [rsp+88h+arg_18], rax
0x180016fd8  mov     rsi, [rsp+88h+var_28]
0x180016fdd  test    rax, rax
0x180016fe0  jz      short loc_18001702E
0x180016fe2  mov     ecx, [rbp+8]
0x180016fe5  mov     [rsp+88h+var_38], ecx
0x180016fe9  mov     [rsp+88h+var_40], 1
0x180016ff1  mov     [rsp+88h+var_48], 0FFFFFFFFFFFFFFFFh
0x180016ffa  mov     rcx, [rsp+88h+var_20]
0x180016fff  mov     [rsp+88h+var_50], rcx
0x180017004  mov     [rsp+88h+var_58], 14h
0x18001700c  mov     [rsp+88h+var_60], rdi
0x180017011  mov     rax, [rbp+40h]
0x180017015  mov     [rsp+88h+var_68], rax
0x18001701a  mov     r9, rsi
0x18001701d  mov     r8, [rbp+20h]
0x180017021  mov     rdx, [rbp+18h]
0x180017025  mov     rcx, r10
0x180017028  call    ??0CPacketRadius@@QEAA@PEAVCHashMD5@@PEAVCHashHmacMD5@@PEAUIIasClient@@PEAVCReportEvent@@PEAEKPEAUsockaddr@@_KW4_porttype_@@H@Z; CPacketRadius::CPacketRadius(CHashMD5 *,CHashHmacMD5 *,IIasClient *,CReportEvent *,uchar *,ulong,sockaddr *,unsigned __int64,_porttype_,int)
0x18001702d  nop
0x18001702e  mov     [r14], rax
0x180017031  test    rax, rax
0x180017034  jnz     short loc_1800170A4
0x180017036  lea     rcx, WPP_GLOBAL_Control
0x18001703d  mov     rax, cs:WPP_GLOBAL_Control
0x180017044  cmp     rax, rcx
0x180017047  jz      short loc_180017087
0x180017049  cmp     byte ptr [rax+19h], 2
0x18001704d  jb      short loc_180017087
0x18001704f  test    dword ptr [rax+1Ch], 100h
0x180017056  jz      short loc_180017087
0x180017058  lea     rcx, aUnableToCreate_2; "Unable to create a Packet-Radius object"...
0x18001705f  call    WppDbgPrint
0x180017064  mov     edx, 1Fh
0x180017069  lea     r9, aNpsrad; "NPSRAD"
0x180017070  lea     r8, WPP_ed9712b053c33f492fa08cace3005bc4_Traceguids
0x180017077  mov     rcx, cs:WPP_GLOBAL_Control
0x18001707e  mov     rcx, [rcx+10h]
0x180017082  call    WPP_SF_s
0x180017087  mov     rax, [rsi]
0x18001708a  mov     rcx, rsi
0x18001708d  mov     rax, [rax+10h]
0x180017091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017096  mov     ebx, 8007000Eh
0x18001709b  mov     rcx, rdi; pv
0x18001709e  call    cs:__imp_CoTaskMemFree
0x1800170a4  mov     eax, ebx
0x1800170a6  lea     r11, [rsp+88h+var_18]
0x1800170ab  mov     rbx, [r11+20h]
0x1800170af  mov     rbp, [r11+28h]
0x1800170b3  mov     rsp, r11
0x1800170b6  pop     r14
0x1800170b8  pop     rdi
0x1800170b9  pop     rsi
0x1800170ba  retn
```
