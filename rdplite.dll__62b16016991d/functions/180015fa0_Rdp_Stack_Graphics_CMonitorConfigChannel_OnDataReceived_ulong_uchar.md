# Rdp::Stack::Graphics::CMonitorConfigChannel::OnDataReceived(ulong,uchar *)

- ea: `0x180015fa0`
- end: `0x1800161b1`
- name: `?OnDataReceived@CMonitorConfigChannel@Graphics@Stack@Rdp@@UEAAJKPEAE@Z`
- size: `529`
- prototype: `__int64 __fastcall(Rdp::Stack::Graphics::CMonitorConfigChannel *__hidden this, unsigned int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x18000cea4`
- `0x18000dbf4`
- `0x180015fa0`
- `0x1800161b8`
- `0x180016304`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016010`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001615c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016010`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001615c`

## string_xrefs

- `0x18001606b`: `onecoreuap\termsrv\rdp_bin\win\rdplite\grfxpipeline\monitorconfigchannel.cpp`
- `0x18001609c`: `Buffer size is too small to cast to RDPCFG_SET_MONITOR_CONFIGURATION_PDU`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Rdp::Stack::Graphics::CMonitorConfigChannel::OnDataReceived(
        Rdp::Stack::Graphics::CMonitorConfigChannel *this,
        unsigned int a2,
        unsigned __int8 *a3)
{
  char v6; // bl
  bool v7; // si
  bool v8; // r14
  char CurrentThreadId; // al
  int v10; // r8d
  int v11; // edx
  const char *v12; // r9
  bool v13; // di
  char v14; // al
  int v15; // r8d
  int v16; // edx
  __int64 result; // rax
  int v18; // [rsp+20h] [rbp-58h]
  int v19; // [rsp+20h] [rbp-58h]
  int v20; // [rsp+28h] [rbp-50h]
  int v21; // [rsp+28h] [rbp-50h]
  char *v22; // [rsp+30h] [rbp-48h]
  char *v23; // [rsp+30h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v6 = 1;
  v7 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v8 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v10) = v8;
    LOBYTE(v11) = v7;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      v10,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v18,
      v20,
      10,
      &WPP_157a04f87712357c49f76c9ea5ffa1bd_Traceguids,
      CurrentThreadId);
  }
  try
  {
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x7D,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfigchannel.cpp",
      (const char *)0x8007007ALL,
      a2 < 0x10,
      (bool)"Buffer size is too small to cast to RDPCFG_PDU_HEADER",
      v22);
    if ( *((_DWORD *)a3 + 3) == 1 )
    {
      wil::details::in1diag3::Throw_HrIfMsg(
        retaddr,
        (void *)0x88,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfigchannel.cpp",
        (const char *)0x8007007ALL,
        *((_DWORD *)a3 + 2) < 8u,
        (bool)"Buffer size is too small to cast to RDPCFG_CAPS_ADVERTISE_PDU",
        v23);
      Rdp::Stack::Graphics::CMonitorConfigChannel::ProcessCapsAdvertise(
        (Rdp::Stack::Graphics::CMonitorConfigChannel *)((char *)this - 80),
        *((_DWORD *)a3 + 2) - 8,
        a3 + 16);
    }
    else if ( *((_DWORD *)a3 + 3) == 3 )
    {
      wil::details::in1diag3::Throw_HrIfMsg(
        retaddr,
        (void *)0x97,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfigchannel.cpp",
        (const char *)0x8007007ALL,
        *((_DWORD *)a3 + 2) < 0x10u,
        (bool)"Buffer size is too small to cast to RDPCFG_SET_MONITOR_CONFIGURATION_PDU",
        v23);
      Rdp::Stack::Graphics::CMonitorConfigChannel::ProcessSetMonitorConfiguration(
        (Rdp::Stack::Graphics::CMonitorConfigChannel *)((char *)this - 80),
        *((_DWORD *)a3 + 5) == 1,
        *((_DWORD *)a3 + 4),
        *((_DWORD *)a3 + 2) - 16,
        a3 + 24);
    }
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v6 = 0;
    }
    v13 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v14 = GetCurrentThreadId();
      LOBYTE(v15) = v13;
      LOBYTE(v16) = v6;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v16,
        v15,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v19,
        v21,
        11,
        &WPP_157a04f87712357c49f76c9ea5ffa1bd_Traceguids,
        v14);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xA7,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfigchannel.cpp",
                           v12);
  }
  return result;
}

```

## disassembly

```asm
0x180015fa0  mov     [rsp+arg_0], rbx
0x180015fa5  mov     [rsp+arg_10], rsi
0x180015faa  push    rdi
0x180015fab  push    r12
0x180015fad  push    r13
0x180015faf  push    r14
0x180015fb1  push    r15
0x180015fb3  sub     rsp, 50h
0x180015fb7  mov     rdi, r8
0x180015fba  mov     r13d, edx
0x180015fbd  mov     r15, rcx
0x180015fc0  lea     rcx, WPP_GLOBAL_Control
0x180015fc7  mov     rax, cs:WPP_GLOBAL_Control
0x180015fce  mov     ebx, 1
0x180015fd3  cmp     rax, rcx
0x180015fd6  jz      short loc_180015FE8
0x180015fd8  test    [rax+1Ch], bl
0x180015fdb  jz      short loc_180015FE8
0x180015fdd  cmp     byte ptr [rax+19h], 4
0x180015fe1  jb      short loc_180015FE8
0x180015fe3  mov     sil, bl
0x180015fe6  jmp     short loc_180015FEB
0x180015fe8  xor     sil, sil
0x180015feb  lea     rax, WPP_RECORDER_INITIALIZED
0x180015ff2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180015ff9  setnz   r14b
0x180015ffd  test    sil, sil
0x180016000  jnz     short loc_180016010
0x180016002  test    r14b, r14b
0x180016005  jnz     short loc_180016010
0x180016007  lea     r12, WPP_157a04f87712357c49f76c9ea5ffa1bd_Traceguids
0x18001600e  jmp     short loc_180016047
0x180016010  call    cs:__imp_GetCurrentThreadId
0x180016016  mov     dword ptr [rsp+78h+var_38], eax; char
0x18001601a  lea     r12, WPP_157a04f87712357c49f76c9ea5ffa1bd_Traceguids
0x180016021  mov     [rsp+78h+MessageGuid], r12; MessageGuid
0x180016026  mov     word ptr [rsp+78h+var_48], 0Ah; char *
0x18001602d  mov     rcx, cs:WPP_GLOBAL_Control
0x180016034  mov     r9, [rcx+28h]; int
0x180016038  mov     r8b, r14b; int
0x18001603b  mov     dl, sil; int
0x18001603e  mov     rcx, [rcx+10h]; int
0x180016042  call    WPP_RECORDER_AND_TRACE_SF_D
0x180016047  cmp     r13d, 10h
0x18001604b  setb    al
0x18001604e  mov     rcx, [rsp+78h]; this
0x180016053  lea     rdx, aBufferSizeIsTo_9; "Buffer size is too small to cast to RDP"...
0x18001605a  mov     qword ptr [rsp+78h+var_50], rdx; bool
0x18001605f  mov     byte ptr [rsp+78h+var_58], al; char
0x180016063  mov     esi, 8007007Ah
0x180016068  mov     r9d, esi; char *
0x18001606b  lea     r14, aOnecoreuapTerm_22; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180016072  mov     r8, r14; unsigned int
0x180016075  mov     edx, 7Dh ; '}'; void *
0x18001607a  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001607f  mov     ecx, [rdi+0Ch]
0x180016082  sub     ecx, 1
0x180016085  jz      short loc_1800160E2
0x180016087  cmp     ecx, 2
0x18001608a  jnz     loc_180016121
0x180016090  cmp     dword ptr [rdi+8], 10h
0x180016094  setb    al
0x180016097  mov     rcx, [rsp+78h]; this
0x18001609c  lea     rdx, aBufferSizeIsTo_2; "Buffer size is too small to cast to RDP"...
0x1800160a3  mov     qword ptr [rsp+78h+var_50], rdx; bool
0x1800160a8  mov     byte ptr [rsp+78h+var_58], al; char
0x1800160ac  mov     r9d, esi; char *
0x1800160af  mov     r8, r14; unsigned int
0x1800160b2  mov     edx, 97h; void *
0x1800160b7  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800160bc  lea     rax, [rdi+18h]
0x1800160c0  mov     r9d, [rdi+8]
0x1800160c4  sub     r9d, 10h; unsigned int
0x1800160c8  cmp     [rdi+14h], ebx
0x1800160cb  setz    dl; bool
0x1800160ce  lea     rcx, [r15-50h]; this
0x1800160d2  mov     [rsp+78h+var_58], rax; void *
0x1800160d7  mov     r8d, [rdi+10h]; unsigned int
0x1800160db  call    ?ProcessSetMonitorConfiguration@CMonitorConfigChannel@Graphics@Stack@Rdp@@AEAAX_NIIPEBX@Z; Rdp::Stack::Graphics::CMonitorConfigChannel::ProcessSetMonitorConfiguration(bool,uint,uint,void const *)
0x1800160e0  jmp     short loc_180016121
0x1800160e2  cmp     dword ptr [rdi+8], 8
0x1800160e6  setb    al
0x1800160e9  mov     rcx, [rsp+78h]; this
0x1800160ee  lea     rdx, aBufferSizeIsTo_6; "Buffer size is too small to cast to RDP"...
0x1800160f5  mov     qword ptr [rsp+78h+var_50], rdx; int
0x1800160fa  mov     byte ptr [rsp+78h+var_58], al; int
0x1800160fe  mov     r9d, esi; char *
0x180016101  mov     r8, r14; unsigned int
0x180016104  mov     edx, 88h; void *
0x180016109  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001610e  lea     r8, [rdi+10h]; void *
0x180016112  mov     edx, [rdi+8]
0x180016115  sub     edx, 8; unsigned int
0x180016118  lea     rcx, [r15-50h]; this
0x18001611c  call    ?ProcessCapsAdvertise@CMonitorConfigChannel@Graphics@Stack@Rdp@@AEAAXIPEBX@Z; Rdp::Stack::Graphics::CMonitorConfigChannel::ProcessCapsAdvertise(uint,void const *)
0x180016121  mov     rax, cs:WPP_GLOBAL_Control
0x180016128  lea     rcx, WPP_GLOBAL_Control
0x18001612f  cmp     rax, rcx
0x180016132  jz      short loc_18001613F
0x180016134  test    [rax+1Ch], bl
0x180016137  jz      short loc_18001613F
0x180016139  cmp     byte ptr [rax+19h], 4
0x18001613d  jnb     short loc_180016141
0x18001613f  xor     bl, bl
0x180016141  lea     rax, WPP_RECORDER_INITIALIZED
0x180016148  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001614f  setnz   dil
0x180016153  test    bl, bl
0x180016155  jnz     short loc_18001615C
0x180016157  test    dil, dil
0x18001615a  jz      short loc_18001618B
0x18001615c  call    cs:__imp_GetCurrentThreadId
0x180016162  mov     dword ptr [rsp+78h+var_38], eax; char
0x180016166  mov     [rsp+78h+MessageGuid], r12; MessageGuid
0x18001616b  mov     word ptr [rsp+78h+var_48], 0Bh; __int16
0x180016172  mov     rcx, cs:WPP_GLOBAL_Control
0x180016179  mov     r9, [rcx+28h]; int
0x18001617d  mov     r8b, dil; int
0x180016180  mov     dl, bl; int
0x180016182  mov     rcx, [rcx+10h]; int
0x180016186  call    WPP_RECORDER_AND_TRACE_SF_D
0x18001618b  xor     eax, eax
0x18001618d  jmp     short loc_180016196
0x18001618f  mov     eax, [rsp+78h+arg_8]
0x180016196  lea     r11, [rsp+78h+var_28]
0x18001619b  mov     rbx, [r11+30h]
0x18001619f  mov     rsi, [r11+40h]
0x1800161a3  mov     rsp, r11
0x1800161a6  pop     r15
0x1800161a8  pop     r14
0x1800161aa  pop     r13
0x1800161ac  pop     r12
0x1800161ae  pop     rdi
0x1800161af  retn
```
