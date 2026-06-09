# CRdpHintApiSink::ReopenVirtualChannel(void)

- ea: `0x140038950`
- end: `0x140038a51`
- name: `?ReopenVirtualChannel@CRdpHintApiSink@@IEAAJXZ`
- size: `257`
- prototype: `__int64 __fastcall(CRdpHintApiSink *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140038190`
- `0x140038420`

## callees

- `0x140004b1c`
- `0x1400056c4`
- `0x14000d350`
- `0x14000efb8`
- `0x140038950`

## import_xrefs

- `WTSAPI32!WTSVirtualChannelOpenEx` at `0x1400389df`
- `WTSAPI32!WTSVirtualChannelOpenEx` at `0x1400389df`
- `WTSAPI32!WTSVirtualChannelClose` at `0x1400389c2`
- `WTSAPI32!WTSVirtualChannelClose` at `0x1400389c2`

## pseudocode

```c
__int64 __fastcall CRdpHintApiSink::ReopenVirtualChannel(CRdpHintApiSink *this)
{
  unsigned int v2; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  void *v4; // rcx
  HANDLE v5; // rax
  unsigned int v6; // eax
  char *v8; // [rsp+30h] [rbp+8h] BYREF

  v2 = 0;
  v8 = (char *)this + 56;
  CTSCriticalSection::Lock((CRdpHintApiSink *)((char *)this + 56));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      52,
      &WPP_831ea65fad7736bfdd6b23908d4018f5_Traceguids,
      CurrentThreadActivityIdPrefix);
  }
  v4 = (void *)*((_QWORD *)this + 148);
  if ( v4 )
  {
    WTSVirtualChannelClose(v4);
    *((_QWORD *)this + 148) = 0;
  }
  v5 = WTSVirtualChannelOpenEx(0xFFFFFFFF, (LPSTR)"Microsoft::Windows::RDS::Geometry::v08.01", 1u);
  *((_QWORD *)this + 148) = v5;
  if ( !v5 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_831ea65fad7736bfdd6b23908d4018f5_Traceguids, v6);
    }
    v2 = -2147467259;
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v8);
  return v2;
}

```

## disassembly

```asm
0x140038950  mov     [rsp+arg_8], rbx
0x140038955  mov     [rsp+arg_10], rbp
0x14003895a  push    rdi
0x14003895b  sub     rsp, 20h
0x14003895f  mov     rbx, rcx
0x140038962  xor     edi, edi
0x140038964  add     rcx, 38h ; '8'; this
0x140038968  mov     [rsp+28h+arg_0], rcx
0x14003896d  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x140038972  mov     rax, cs:WPP_GLOBAL_Control
0x140038979  lea     rbp, WPP_GLOBAL_Control
0x140038980  cmp     rax, rbp
0x140038983  jz      short loc_1400389B6
0x140038985  test    dword ptr [rax+1Ch], 200h
0x14003898c  jz      short loc_1400389B6
0x14003898e  cmp     byte ptr [rax+19h], 5
0x140038992  jb      short loc_1400389B6
0x140038994  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140038999  mov     rcx, cs:WPP_GLOBAL_Control
0x1400389a0  lea     edx, [rdi+34h]
0x1400389a3  mov     r9d, eax
0x1400389a6  lea     r8, WPP_831ea65fad7736bfdd6b23908d4018f5_Traceguids
0x1400389ad  mov     rcx, [rcx+10h]
0x1400389b1  call    WPP_SF_d
0x1400389b6  mov     rcx, [rbx+4A0h]; hChannelHandle
0x1400389bd  test    rcx, rcx
0x1400389c0  jz      short loc_1400389CF
0x1400389c2  call    cs:__imp_WTSVirtualChannelClose
0x1400389c8  mov     [rbx+4A0h], rdi
0x1400389cf  mov     r8d, 1; flags
0x1400389d5  lea     rdx, pVirtualName; "Microsoft::Windows::RDS::Geometry::v08."...
0x1400389dc  or      ecx, 0FFFFFFFFh; SessionId
0x1400389df  call    cs:__imp_WTSVirtualChannelOpenEx
0x1400389e5  mov     [rbx+4A0h], rax
0x1400389ec  test    rax, rax
0x1400389ef  jnz     short loc_140038A35
0x1400389f1  mov     rax, cs:WPP_GLOBAL_Control
0x1400389f8  cmp     rax, rbp
0x1400389fb  jz      short loc_140038A30
0x1400389fd  test    dword ptr [rax+1Ch], 200h
0x140038a04  jz      short loc_140038A30
0x140038a06  cmp     byte ptr [rax+19h], 2
0x140038a0a  jb      short loc_140038A30
0x140038a0c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140038a11  mov     rcx, cs:WPP_GLOBAL_Control
0x140038a18  lea     r8, WPP_831ea65fad7736bfdd6b23908d4018f5_Traceguids
0x140038a1f  mov     edx, 35h ; '5'
0x140038a24  mov     r9d, eax
0x140038a27  mov     rcx, [rcx+10h]
0x140038a2b  call    WPP_SF_d
0x140038a30  mov     edi, 80004005h
0x140038a35  lea     rcx, [rsp+28h+arg_0]; this
0x140038a3a  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x140038a3f  mov     rbx, [rsp+28h+arg_8]
0x140038a44  mov     eax, edi
0x140038a46  mov     rbp, [rsp+28h+arg_10]
0x140038a4b  add     rsp, 20h
0x140038a4f  pop     rdi
0x140038a50  retn
```
