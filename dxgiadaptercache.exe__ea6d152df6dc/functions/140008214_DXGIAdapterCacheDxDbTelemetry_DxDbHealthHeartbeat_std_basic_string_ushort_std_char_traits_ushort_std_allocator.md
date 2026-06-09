# DXGIAdapterCacheDxDbTelemetry::DxDbHealthHeartbeat_(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,long,ushort const *,long,ushort const *,long,uint,long,ushort const *,ushort const *,uint,ushort const *,long,ushort const *,long,uint)

- ea: `0x140008214`
- end: `0x1400083c6`
- name: `?DxDbHealthHeartbeat_@DXGIAdapterCacheDxDbTelemetry@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@JPEBGJ1JIJ11I1J1JI@Z`
- size: `434`
- prototype: `__int64 __fastcall(__int64, __int64 *, int, __int64 *, int, __int64 *, int, int, int, __int64 *, __int64 *, int, __int64 *, int, __int64 *, int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14000eafc`

## callees

- `0x1400012bc`
- `0x140008214`
- `0x14000aa74`

## pseudocode

```c
__int64 __fastcall DXGIAdapterCacheDxDbTelemetry::DxDbHealthHeartbeat_(
        __int64 a1,
        __int64 *a2,
        int a3,
        __int64 *a4,
        int a5,
        __int64 *a6,
        int a7,
        int a8,
        int a9,
        __int64 *a10,
        __int64 *a11,
        int a12,
        __int64 *a13,
        int a14,
        __int64 *a15,
        int a16,
        int a17)
{
  __int64 result; // rax
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // r10
  bool v24; // cf
  bool v25; // zf
  int v26; // [rsp+B0h] [rbp-80h] BYREF
  int v27; // [rsp+B4h] [rbp-7Ch] BYREF
  int v28; // [rsp+B8h] [rbp-78h] BYREF
  int v29; // [rsp+BCh] [rbp-74h] BYREF
  int v30; // [rsp+C0h] [rbp-70h] BYREF
  int v31; // [rsp+C4h] [rbp-6Ch] BYREF
  int v32; // [rsp+C8h] [rbp-68h] BYREF
  int v33; // [rsp+CCh] [rbp-64h] BYREF
  int v34; // [rsp+D0h] [rbp-60h] BYREF
  __int64 *v35; // [rsp+D8h] [rbp-58h] BYREF
  __int64 *v36; // [rsp+E0h] [rbp-50h] BYREF
  __int64 *v37; // [rsp+E8h] [rbp-48h] BYREF
  __int64 *v38; // [rsp+F0h] [rbp-40h] BYREF
  __int64 *v39; // [rsp+F8h] [rbp-38h] BYREF
  __int64 *v40; // [rsp+100h] [rbp-30h] BYREF
  __int64 *v41; // [rsp+108h] [rbp-28h] BYREF
  __int64 v42[6]; // [rsp+110h] [rbp-20h] BYREF
  __int64 v43; // [rsp+150h] [rbp+20h] BYREF

  v43 = a1;
  result = (__int64)DirectXDatabaseUpdaterLogging::Provider();
  v23 = result;
  if ( *(_DWORD *)result > 5u )
  {
    result = *(_QWORD *)(result + 24);
    if ( (*(_QWORD *)(v23 + 16) & 0x400000000000LL) != 0 && (result & 0x400000000000LL) == result )
    {
      v24 = (unsigned __int64)a2[3] < 7;
      v25 = a2[3] == 7;
      v26 = a17;
      v27 = a16;
      v35 = a15;
      v28 = a14;
      v36 = a13;
      v29 = a12;
      v37 = a11;
      v38 = a10;
      v30 = a9;
      v31 = a8;
      v32 = a7;
      v39 = a6;
      v33 = a5;
      v40 = a4;
      v34 = a3;
      if ( !v24 && !v25 )
        a2 = (__int64 *)*a2;
      v41 = a2;
      LOBYTE(v43) = 1;
      v42[0] = 0x2000000;
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
               v23,
               (__int64)byte_1400153E5,
               v21,
               v22,
               (__int64)v42,
               (__int64)&v43,
               &v41,
               (__int64)&v34,
               &v40,
               (__int64)&v33,
               &v39,
               (__int64)&v32,
               (__int64)&v31,
               (__int64)&v30,
               &v38,
               &v37,
               (__int64)&v29,
               &v36,
               (__int64)&v28,
               &v35,
               (__int64)&v27,
               (__int64)&v26);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140008214  mov     [rsp-8+arg_0], rcx
0x140008219  push    rbp
0x14000821a  push    rbx
0x14000821b  push    rsi
0x14000821c  push    rdi
0x14000821d  lea     rbp, [rsp+8]
0x140008222  sub     rsp, 128h
0x140008229  mov     rdi, r9
0x14000822c  mov     esi, r8d
0x14000822f  mov     rbx, rdx
0x140008232  call    ?Provider@DirectXDatabaseUpdaterLogging@@SAPEBU_tlgProvider_t@@XZ; DirectXDatabaseUpdaterLogging::Provider(void)
0x140008237  mov     r10, rax
0x14000823a  mov     ecx, [rax]
0x14000823c  cmp     ecx, 5
0x14000823f  jbe     loc_1400083BA
0x140008245  mov     rax, [rax+18h]
0x140008249  mov     rdx, 400000000000h
0x140008253  mov     rcx, [r10+10h]
0x140008257  test    rdx, rcx
0x14000825a  jz      loc_1400083BA
0x140008260  mov     rcx, rax
0x140008263  and     rcx, rdx
0x140008266  cmp     rcx, rax
0x140008269  jnz     loc_1400083BA
0x14000826f  cmp     qword ptr [rbx+18h], 7
0x140008274  mov     eax, [rbp+10h+arg_80]
0x14000827a  mov     [rbp+10h+var_90], eax
0x14000827d  mov     eax, [rbp+10h+arg_78]
0x140008283  mov     [rbp+10h+var_8C], eax
0x140008286  mov     rax, [rbp+10h+arg_70]
0x14000828d  mov     [rbp+10h+var_68], rax
0x140008291  mov     eax, [rbp+10h+arg_68]
0x140008297  mov     [rbp+10h+var_88], eax
0x14000829a  mov     rax, [rbp+10h+arg_60]
0x1400082a1  mov     [rbp+10h+var_60], rax
0x1400082a5  mov     eax, [rbp+10h+arg_58]
0x1400082a8  mov     [rbp+10h+var_84], eax
0x1400082ab  mov     rax, [rbp+10h+arg_50]
0x1400082af  mov     [rbp+10h+var_58], rax
0x1400082b3  mov     rax, [rbp+10h+arg_48]
0x1400082b7  mov     [rbp+10h+var_50], rax
0x1400082bb  mov     eax, [rbp+10h+arg_40]
0x1400082be  mov     [rbp+10h+var_80], eax
0x1400082c1  mov     eax, [rbp+10h+arg_38]
0x1400082c4  mov     [rbp+10h+var_7C], eax
0x1400082c7  mov     eax, [rbp+10h+arg_30]
0x1400082ca  mov     [rbp+10h+var_78], eax
0x1400082cd  mov     rax, [rbp+10h+arg_28]
0x1400082d1  mov     [rbp+10h+var_48], rax
0x1400082d5  mov     eax, [rbp+10h+arg_20]
0x1400082d8  mov     [rbp+10h+var_74], eax
0x1400082db  mov     [rbp+10h+var_40], rdi
0x1400082df  mov     [rbp+10h+var_70], esi
0x1400082e2  jbe     short loc_1400082E7
0x1400082e4  mov     rbx, [rbx]
0x1400082e7  lea     rax, [rbp+10h+var_90]
0x1400082eb  mov     [rbp+10h+var_38], rbx
0x1400082ef  mov     [rsp+140h+var_98], rax
0x1400082f7  lea     rdx, byte_1400153E5
0x1400082fe  lea     rax, [rbp+10h+var_8C]
0x140008302  mov     byte ptr [rbp+10h+arg_0], 1
0x140008306  mov     [rsp+140h+var_A0], rax
0x14000830e  mov     rcx, r10
0x140008311  lea     rax, [rbp+10h+var_68]
0x140008315  mov     [rbp+10h+var_30], 2000000h
0x14000831d  mov     [rsp+140h+var_A8], rax
0x140008325  lea     rax, [rbp+10h+var_88]
0x140008329  mov     [rsp+140h+var_B0], rax
0x140008331  lea     rax, [rbp+10h+var_60]
0x140008335  mov     [rsp+140h+var_B8], rax
0x14000833d  lea     rax, [rbp+10h+var_84]
0x140008341  mov     [rsp+140h+var_C0], rax
0x140008349  lea     rax, [rbp+10h+var_58]
0x14000834d  mov     [rsp+140h+var_C8], rax
0x140008352  lea     rax, [rbp+10h+var_50]
0x140008356  mov     [rsp+140h+var_D0], rax
0x14000835b  lea     rax, [rbp+10h+var_80]
0x14000835f  mov     [rsp+140h+var_D8], rax
0x140008364  lea     rax, [rbp+10h+var_7C]
0x140008368  mov     [rsp+140h+var_E0], rax
0x14000836d  lea     rax, [rbp+10h+var_78]
0x140008371  mov     [rsp+140h+var_E8], rax
0x140008376  lea     rax, [rbp+10h+var_48]
0x14000837a  mov     [rsp+140h+var_F0], rax
0x14000837f  lea     rax, [rbp+10h+var_74]
0x140008383  mov     [rsp+140h+var_F8], rax
0x140008388  lea     rax, [rbp+10h+var_40]
0x14000838c  mov     [rsp+140h+var_100], rax
0x140008391  lea     rax, [rbp+10h+var_70]
0x140008395  mov     [rsp+140h+var_108], rax
0x14000839a  lea     rax, [rbp+10h+var_38]
0x14000839e  mov     [rsp+140h+var_110], rax
0x1400083a3  lea     rax, [rbp+10h+arg_0]
0x1400083a7  mov     [rsp+140h+var_118], rax
0x1400083ac  lea     rax, [rbp+10h+var_30]
0x1400083b0  mov     [rsp+140h+var_120], rax
0x1400083b5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U4@U3@U4@U4@U4@U3@U3@U4@U3@U4@U3@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@56566655656566@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400083ba  add     rsp, 128h
0x1400083c1  pop     rdi
0x1400083c2  pop     rsi
0x1400083c3  pop     rbx
0x1400083c4  pop     rbp
0x1400083c5  retn
```
