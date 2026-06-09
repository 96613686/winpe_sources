# ATL::IDispEventSimpleImpl<1,CRedbookWriterEvent,&_GUID const IID_DDiscFormat2TrackAtOnceEvents>::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x180015fa0`
- end: `0x180016173`
- name: `?Invoke@?$IDispEventSimpleImpl@$00VCRedbookWriterEvent@@$1?IID_DDiscFormat2TrackAtOnceEvents@@3U_GUID@@B@ATL@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `467`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int, int, VARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001a94`
- `0x180001b04`
- `0x180015fa0`
- `0x180016224`
- `0x180018500`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::IDispEventSimpleImpl<1,CRedbookWriterEvent,&_GUID const IID_DDiscFormat2TrackAtOnceEvents>::Invoke(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        int a5,
        int a6,
        VARIANT *a7)
{
  __int64 *v10; // rbx
  _QWORD *v11; // rax
  int *v12; // r8
  int v14[4]; // [rsp+30h] [rbp-58h] BYREF
  int v15[4]; // [rsp+40h] [rbp-48h] BYREF
  __int64 v16; // [rsp+50h] [rbp-38h]

  if ( __TSS0__1___GetSinkMap_CRedbookWriterEvent__SAPEBU___ATL_EVENT_ENTRY_VCRedbookWriterEvent___ATL__XZ_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL) )
  {
    Init_thread_header(&__TSS0__1___GetSinkMap_CRedbookWriterEvent__SAPEBU___ATL_EVENT_ENTRY_VCRedbookWriterEvent___ATL__XZ_4HA);
    if ( __TSS0__1___GetSinkMap_CRedbookWriterEvent__SAPEBU___ATL_EVENT_ENTRY_VCRedbookWriterEvent___ATL__XZ_4HA == -1 )
    {
      dword_180021330 = 0;
      qword_180021328 = (__int64) CRedbookWriterEvent::`vcall'{56,{flat}};
      dword_180021334 = v14[3];
      dword_180021364 = v14[3];
      qword_180021338 = 0;
      dword_180021340 = 0;
      qword_180021348 = 0;
      qword_180021350 = 0;
      qword_180021358 = 0;
      dword_180021360 = 0;
      qword_180021368 = 0;
      Init_thread_footer(&__TSS0__1___GetSinkMap_CRedbookWriterEvent__SAPEBU___ATL_EVENT_ENTRY_VCRedbookWriterEvent___ATL__XZ_4HA);
    }
  }
  v10 = &`CRedbookWriterEvent::_GetSinkMap'::`2'::map;
  if ( off_180021318 )
  {
    while ( 1 )
    {
      if ( *(_DWORD *)v10 == 1 && *((_DWORD *)v10 + 5) == a2 )
      {
        v11 = (_QWORD *)v10[1];
        if ( *v11 == *(_QWORD *)&IID_DDiscFormat2TrackAtOnceEvents.Data1
          && v11[1] == *(_QWORD *)IID_DDiscFormat2TrackAtOnceEvents.Data4 )
        {
          break;
        }
      }
      if ( !v10[7] )
        return 0;
      v10 += 6;
    }
    v12 = (int *)v10[5];
    v16 = 0;
    *(_OWORD *)v15 = 0;
    if ( v12 )
      goto LABEL_12;
    if ( (*(int (__fastcall **)(__int64, GUID *, _QWORD, _QWORD, int *))(*(_QWORD *)a1 + 56LL))(
           a1,
           &IID_DDiscFormat2TrackAtOnceEvents,
           a2,
           a4,
           v15) >= 0 )
    {
      v12 = v15;
LABEL_12:
      *(_OWORD *)v14 = *(_OWORD *)(v10 + 3);
      return ATL::IDispEventSimpleImpl<1,CRedbookWriterEvent,&_GUID const IID_DDiscFormat2TrackAtOnceEvents>::InvokeFromFuncInfo(
               a1,
               (int)v14,
               (int)v12,
               a6,
               a7);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180015fa0  mov     [rsp+arg_10], rbx
0x180015fa5  push    rbp
0x180015fa6  push    rsi
0x180015fa7  push    rdi
0x180015fa8  push    r14
0x180015faa  push    r15
0x180015fac  sub     rsp, 60h
0x180015fb0  mov     rax, cs:__security_cookie
0x180015fb7  xor     rax, rsp
0x180015fba  mov     [rsp+88h+var_30], rax
0x180015fbf  mov     rax, gs:58h
0x180015fc8  mov     rsi, rcx
0x180015fcb  mov     ecx, cs:_tls_index
0x180015fd1  mov     edi, edx
0x180015fd3  mov     rbp, qword ptr [rsp+88h+arg_28]
0x180015fdb  mov     r15d, r9d
0x180015fde  mov     r14, [rsp+88h+arg_30]
0x180015fe6  mov     edx, 4
0x180015feb  mov     rax, [rax+rcx*8]
0x180015fef  mov     eax, [rdx+rax]
0x180015ff2  cmp     cs:?$TSS0@?1??_GetSinkMap@CRedbookWriterEvent@@SAPEBU?$_ATL_EVENT_ENTRY@VCRedbookWriterEvent@@@ATL@@XZ@4HA, eax
0x180015ff8  jg      loc_1800160D2
0x180015ffe  cmp     cs:off_180021318, 0
0x180016006  lea     rbx, ?map@?1??_GetSinkMap@CRedbookWriterEvent@@SAPEBU?$_ATL_EVENT_ENTRY@VCRedbookWriterEvent@@@ATL@@XZ@4QBU34@B; ATL::_ATL_EVENT_ENTRY<CRedbookWriterEvent> const near * const `CRedbookWriterEvent::_GetSinkMap(void)'::`2'::map
0x18001600d  jz      loc_1800160AF
0x180016013  mov     rcx, qword ptr cs:IID_DDiscFormat2TrackAtOnceEvents.Data4
0x18001601a  mov     rdx, qword ptr cs:IID_DDiscFormat2TrackAtOnceEvents.Data1
0x180016021  cmp     dword ptr [rbx], 1
0x180016024  jnz     short loc_18001603A
0x180016026  cmp     [rbx+14h], edi
0x180016029  jnz     short loc_18001603A
0x18001602b  mov     rax, [rbx+8]
0x18001602f  cmp     [rax], rdx
0x180016032  jnz     short loc_18001603A
0x180016034  cmp     [rax+8], rcx
0x180016038  jz      short loc_180016047
0x18001603a  cmp     qword ptr [rbx+38h], 0
0x18001603f  jz      short loc_1800160AF
0x180016041  add     rbx, 30h ; '0'
0x180016045  jmp     short loc_180016021
0x180016047  mov     r8, [rbx+28h]
0x18001604b  xor     eax, eax
0x18001604d  mov     [rsp+88h+var_38], rax
0x180016052  xorps   xmm0, xmm0
0x180016055  movups  xmmword ptr [rsp+88h+var_48], xmm0
0x18001605a  test    r8, r8
0x18001605d  jnz     short loc_18001608E
0x18001605f  mov     rax, [rsi]
0x180016062  lea     rcx, [rsp+88h+var_48]
0x180016067  mov     [rsp+88h+var_68], rcx
0x18001606c  lea     rdx, IID_DDiscFormat2TrackAtOnceEvents
0x180016073  mov     r9d, r15d
0x180016076  mov     r8d, edi
0x180016079  mov     rcx, rsi
0x18001607c  mov     rax, [rax+38h]
0x180016080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016085  test    eax, eax
0x180016087  js      short loc_1800160AF
0x180016089  lea     r8, [rsp+88h+var_48]; int
0x18001608e  movups  xmm0, xmmword ptr [rbx+18h]
0x180016092  mov     r9, rbp; int
0x180016095  mov     [rsp+88h+var_68], r14; VARIANT *
0x18001609a  lea     rdx, [rsp+88h+var_58]; int
0x18001609f  mov     rcx, rsi; int
0x1800160a2  movdqu  xmmword ptr [rsp+88h+var_58], xmm0
0x1800160a8  call    ?InvokeFromFuncInfo@?$IDispEventSimpleImpl@$00VCRedbookWriterEvent@@$1?IID_DDiscFormat2TrackAtOnceEvents@@3U_GUID@@B@ATL@@QEAAJP8CRedbookWriterEvent@@EAAXXZAEAU_ATL_FUNC_INFO@2@PEAUtagDISPPARAMS@@PEAUtagVARIANT@@@Z; ATL::IDispEventSimpleImpl<1,CRedbookWriterEvent,&_GUID const IID_DDiscFormat2TrackAtOnceEvents>::InvokeFromFuncInfo(void (CRedbookWriterEvent::*)(void),ATL::_ATL_FUNC_INFO &,tagDISPPARAMS *,tagVARIANT *)
0x1800160ad  jmp     short loc_1800160B1
0x1800160af  xor     eax, eax
0x1800160b1  mov     rcx, [rsp+88h+var_30]
0x1800160b6  xor     rcx, rsp; StackCookie
0x1800160b9  call    __security_check_cookie
0x1800160be  mov     rbx, [rsp+88h+arg_10]
0x1800160c6  add     rsp, 60h
0x1800160ca  pop     r15
0x1800160cc  pop     r14
0x1800160ce  pop     rdi
0x1800160cf  pop     rsi
0x1800160d0  pop     rbp
0x1800160d1  retn
0x1800160d2  lea     rcx, ?$TSS0@?1??_GetSinkMap@CRedbookWriterEvent@@SAPEBU?$_ATL_EVENT_ENTRY@VCRedbookWriterEvent@@@ATL@@XZ@4HA
0x1800160d9  call    _Init_thread_header
0x1800160de  cmp     cs:?$TSS0@?1??_GetSinkMap@CRedbookWriterEvent@@SAPEBU?$_ATL_EVENT_ENTRY@VCRedbookWriterEvent@@@ATL@@XZ@4HA, 0FFFFFFFFh
0x1800160e5  jnz     loc_180015FFE
0x1800160eb  lea     rax, ??_9CRedbookWriterEvent@@$BDI@AA; [thunk]: CRedbookWriterEvent::`vcall'{56,{flat}}
0x1800160f2  mov     cs:dword_180021330, 0
0x1800160fc  mov     cs:qword_180021328, rax
0x180016103  lea     rcx, ?$TSS0@?1??_GetSinkMap@CRedbookWriterEvent@@SAPEBU?$_ATL_EVENT_ENTRY@VCRedbookWriterEvent@@@ATL@@XZ@4HA
0x18001610a  mov     eax, [rsp+88h+var_58+0Ch]
0x18001610e  mov     cs:dword_180021334, eax
0x180016114  mov     eax, [rsp+88h+var_58+0Ch]
0x180016118  mov     cs:dword_180021364, eax
0x18001611e  mov     cs:qword_180021338, 0
0x180016129  mov     cs:dword_180021340, 0
0x180016133  mov     cs:qword_180021348, 0
0x18001613e  mov     cs:qword_180021350, 0
0x180016149  mov     cs:qword_180021358, 0
0x180016154  mov     cs:dword_180021360, 0
0x18001615e  mov     cs:qword_180021368, 0
0x180016169  call    _Init_thread_footer
0x18001616e  jmp     loc_180015FFE
```
