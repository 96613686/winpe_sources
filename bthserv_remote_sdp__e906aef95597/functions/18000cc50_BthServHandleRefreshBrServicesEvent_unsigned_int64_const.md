# BthServHandleRefreshBrServicesEvent(unsigned __int64 const &)

- ea: `0x18000cc50`
- end: `0x18000ce42`
- name: `?BthServHandleRefreshBrServicesEvent@@YAXAEB_K@Z`
- size: `498`
- prototype: `void __fastcall(const unsigned __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000e210`

## callees

- `0x180001bcc`
- `0x18000cc50`
- `0x180012004`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000cd15`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000cd15`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cdd2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cdd2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cce3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cce3`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000cd66`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000cd66`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall BthServHandleRefreshBrServicesEvent(const unsigned __int64 *a1)
{
  char v2; // bl
  bool v3; // dl
  PSRWLOCK v4; // rdi
  unsigned __int64 v5; // rbp
  _QWORD *Ptr; // r14
  _QWORD *v7; // rax
  _QWORD *v8; // rcx
  _BYTE *v9; // rcx
  bool v10; // dl

  v2 = 1;
  v3 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v3,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  v4 = qword_180047110;
  v5 = *a1 & 0xFFFFFFFFFFFFLL;
  AcquireSRWLockExclusive(qword_180047110);
  Ptr = v4[2].Ptr;
  if ( v4[3].Ptr == (PVOID)0x7FFFFFFFFFFFFFFLL )
    std::_Xlength_error("list too long");
  v7 = operator new(0x20u);
  v7[3] = v5;
  v7[2] = &Microsoft::Bluetooth::BluetoothBRAddress::`vftable';
  ++v4[3].Ptr;
  v8 = (_QWORD *)Ptr[1];
  *v7 = Ptr;
  v7[1] = v8;
  Ptr[1] = v7;
  *v8 = v7;
  if ( !LOBYTE(v4[1].Ptr) )
  {
    SubmitThreadpoolWork((PTP_WORK)v4[4].Ptr);
    LOBYTE(v4[1].Ptr) = 1;
LABEL_19:
    v9 = WPP_GLOBAL_Control;
    goto LABEL_20;
  }
  v9 = WPP_GLOBAL_Control;
  v10 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  if ( v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v10,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
    goto LABEL_19;
  }
LABEL_20:
  if ( v4 )
  {
    ReleaseSRWLockExclusive(v4);
    v9 = WPP_GLOBAL_Control;
  }
  if ( v9 == (_BYTE *)&WPP_GLOBAL_Control || v9[25] < 5u )
    v2 = 0;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)v9 + 2),
      v2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)v9 + 5));
}

```

## disassembly

```asm
0x18000cc50  mov     [rsp+arg_8], rbx
0x18000cc55  mov     [rsp+arg_10], rbp
0x18000cc5a  push    rsi
0x18000cc5b  push    rdi
0x18000cc5c  push    r12
0x18000cc5e  push    r13
0x18000cc60  push    r14
0x18000cc62  sub     rsp, 60h
0x18000cc66  mov     rbp, rcx
0x18000cc69  lea     r12, WPP_GLOBAL_Control
0x18000cc70  mov     ebx, 1
0x18000cc75  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cc7c  cmp     rcx, r12
0x18000cc7f  jz      short loc_18000CC8B
0x18000cc81  cmp     byte ptr [rcx+19h], 5
0x18000cc85  jb      short loc_18000CC8B
0x18000cc87  mov     dl, bl
0x18000cc89  jmp     short loc_18000CC8D
0x18000cc8b  xor     dl, dl
0x18000cc8d  lea     r13, WPP_RECORDER_INITIALIZED
0x18000cc94  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18000cc9b  setnz   r8b
0x18000cc9f  lea     r9, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x18000cca6  test    dl, dl
0x18000cca8  jnz     short loc_18000CCAF
0x18000ccaa  test    r8b, r8b
0x18000ccad  jz      short loc_18000CCC8
0x18000ccaf  mov     [rsp+88h+var_50], r9
0x18000ccb4  mov     [rsp+88h+var_58], 7Eh ; '~'
0x18000ccbb  mov     r9, [rcx+28h]
0x18000ccbf  mov     rcx, [rcx+10h]
0x18000ccc3  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000ccc8  mov     rdi, cs:qword_180047110
0x18000cccf  mov     rbp, [rbp+0]
0x18000ccd3  mov     rax, 0FFFFFFFFFFFFh
0x18000ccdd  and     rbp, rax
0x18000cce0  mov     rcx, rdi; SRWLock
0x18000cce3  call    cs:__imp_AcquireSRWLockExclusive
0x18000ccea  nop     dword ptr [rax+rax+00h]
0x18000ccef  mov     [rsp+88h+arg_0], rdi
0x18000ccf7  lea     rsi, [rdi+10h]
0x18000ccfb  mov     r14, [rsi]
0x18000ccfe  mov     rax, 7FFFFFFFFFFFFFFh
0x18000cd08  cmp     [rsi+8], rax
0x18000cd0c  jnz     short loc_18000CD22
0x18000cd0e  lea     rcx, aListTooLong; "list too long"
0x18000cd15  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000cd22  mov     [rsp+88h+var_38], rsi
0x18000cd27  and     [rsp+88h+var_30], 0
0x18000cd2d  mov     ecx, 20h ; ' '; Size
0x18000cd32  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000cd37  mov     [rax+18h], rbp
0x18000cd3b  lea     rcx, ??_7BluetoothBRAddress@Bluetooth@Microsoft@@6B@; const Microsoft::Bluetooth::BluetoothBRAddress::`vftable'
0x18000cd42  mov     [rax+10h], rcx
0x18000cd46  add     [rsi+8], rbx
0x18000cd4a  mov     rcx, [r14+8]
0x18000cd4e  mov     [rax], r14
0x18000cd51  mov     [rax+8], rcx
0x18000cd55  mov     [r14+8], rax
0x18000cd59  mov     [rcx], rax
0x18000cd5c  cmp     byte ptr [rdi+8], 0
0x18000cd60  jnz     short loc_18000CD77
0x18000cd62  mov     rcx, [rdi+20h]; pwk
0x18000cd66  call    cs:__imp_SubmitThreadpoolWork
0x18000cd6d  nop     dword ptr [rax+rax+00h]
0x18000cd72  mov     [rdi+8], bl
0x18000cd75  jmp     short loc_18000CDC3
0x18000cd77  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cd7e  cmp     rcx, r12
0x18000cd81  jz      short loc_18000CD8D
0x18000cd83  cmp     byte ptr [rcx+19h], 5
0x18000cd87  jb      short loc_18000CD8D
0x18000cd89  mov     dl, bl
0x18000cd8b  jmp     short loc_18000CD8F
0x18000cd8d  xor     dl, dl
0x18000cd8f  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18000cd96  setnz   r8b
0x18000cd9a  test    dl, dl
0x18000cd9c  jnz     short loc_18000CDA3
0x18000cd9e  test    r8b, r8b
0x18000cda1  jz      short loc_18000CDCA
0x18000cda3  lea     rax, WPP_21eeecb372ac35bdc1c1ea9e0d2ef949_Traceguids
0x18000cdaa  mov     [rsp+88h+var_50], rax
0x18000cdaf  mov     [rsp+88h+var_58], 0Ah
0x18000cdb6  mov     r9, [rcx+28h]
0x18000cdba  mov     rcx, [rcx+10h]
0x18000cdbe  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000cdc3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cdca  test    rdi, rdi
0x18000cdcd  jz      short loc_18000CDE5
0x18000cdcf  mov     rcx, rdi; SRWLock
0x18000cdd2  call    cs:__imp_ReleaseSRWLockExclusive
0x18000cdd9  nop     dword ptr [rax+rax+00h]
0x18000cdde  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cde5  cmp     rcx, r12
0x18000cde8  jz      short loc_18000CDF0
0x18000cdea  cmp     byte ptr [rcx+19h], 5
0x18000cdee  jnb     short loc_18000CDF2
0x18000cdf0  xor     bl, bl
0x18000cdf2  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18000cdf9  setnz   r8b
0x18000cdfd  test    bl, bl
0x18000cdff  jnz     short loc_18000CE06
0x18000ce01  test    r8b, r8b
0x18000ce04  jz      short loc_18000CE28
0x18000ce06  lea     rdx, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x18000ce0d  mov     [rsp+88h+var_50], rdx
0x18000ce12  mov     [rsp+88h+var_58], 7Fh
0x18000ce19  mov     r9, [rcx+28h]
0x18000ce1d  mov     dl, bl
0x18000ce1f  mov     rcx, [rcx+10h]
0x18000ce23  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000ce28  lea     r11, [rsp+88h+var_28]
0x18000ce2d  mov     rbx, [r11+38h]
0x18000ce31  mov     rbp, [r11+40h]
0x18000ce35  mov     rsp, r11
0x18000ce38  pop     r14
0x18000ce3a  pop     r13
0x18000ce3c  pop     r12
0x18000ce3e  pop     rdi
0x18000ce3f  pop     rsi
0x18000ce40  retn
```
