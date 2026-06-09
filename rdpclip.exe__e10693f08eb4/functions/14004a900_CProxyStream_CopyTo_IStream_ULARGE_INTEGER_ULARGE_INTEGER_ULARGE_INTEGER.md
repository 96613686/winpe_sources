# CProxyStream::CopyTo(IStream *,_ULARGE_INTEGER,_ULARGE_INTEGER *,_ULARGE_INTEGER *)

- ea: `0x14004a900`
- end: `0x14004abb9`
- name: `?CopyTo@CProxyStream@@UEAAJPEAUIStream@@T_ULARGE_INTEGER@@PEAT3@2@Z`
- size: `697`
- prototype: `__int64 __usercall@<rax>(CProxyStream *__hidden this@<rcx>, struct IStream *@<rdx>, union _ULARGE_INTEGER@<r8>, union _ULARGE_INTEGER *@<r9>, union _ULARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x1400030d3`
- `0x140004b1c`
- `0x1400056c4`
- `0x140005750`
- `0x140011054`
- `0x1400186e4`
- `0x14004a900`
- `0x14004b5e0`
- `0x14004c1c0`
- `0x14006b010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004ab99`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004ab99`

## string_xrefs

- `0x14004ab70`: `Write failed!`
- `0x14004aae4`: `Read failed!`

## pseudocode

```c
__int64 __fastcall CProxyStream::CopyTo(
        DWORD *this,
        struct IStream *a2,
        union _ULARGE_INTEGER a3,
        union _ULARGE_INTEGER *a4,
        union _ULARGE_INTEGER *a5)
{
  DWORD LowPart; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v10; // ebx
  unsigned int v11; // eax
  void *v12; // rax
  void *v13; // rsi
  unsigned int v14; // eax
  unsigned int v15; // eax
  int v16; // edx
  const char *v17; // rcx
  __int64 v18; // r8
  _DWORD v20[4]; // [rsp+30h] [rbp-78h] BYREF
  _BYTE v21[80]; // [rsp+40h] [rbp-68h] BYREF
  unsigned int v22; // [rsp+B8h] [rbp+10h] BYREF
  union _ULARGE_INTEGER v23; // [rsp+C0h] [rbp+18h]

  v23 = a3;
  v22 = 0;
  v20[0] = 0;
  LowPart = a3.LowPart;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        61,
        &WPP_c4d247ff647635a25b2fe01fcd88288b_Traceguids,
        CurrentThreadActivityIdPrefix);
    }
    return (unsigned int)-2147287031;
  }
  if ( a3.LowPart == -1 && v23.HighPart == -1 )
  {
    memset_0(v21, 0, sizeof(v21));
    v10 = CProxyStream::Stat((CProxyStream *)this, (struct tagSTATSTG *)v21, 1u);
    if ( v10 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          62,
          (unsigned int)&WPP_c4d247ff647635a25b2fe01fcd88288b_Traceguids,
          v11,
          (__int64)"Stat failed!",
          v10);
      }
      return (unsigned int)v10;
    }
    LowPart = this[8];
  }
  v12 = (void *)PAL_System_MemAlloc(LowPart);
  v13 = v12;
  if ( v12 )
  {
    v10 = CProxyStream::Read((CProxyStream *)this, v12, LowPart, &v22);
    if ( v10 >= 0 )
    {
      v18 = v22;
      if ( a4 )
        a4->QuadPart = v22;
      v10 = (*(__int64 (__fastcall **)(struct IStream *, void *, __int64, _DWORD *))(*(_QWORD *)a2 + 32LL))(
              a2,
              v13,
              v18,
              v20);
      if ( v10 >= 0 )
      {
        if ( a5 )
          a5->QuadPart = v20[0];
        goto LABEL_36;
      }
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_36:
        LocalFree(v13);
        return (unsigned int)v10;
      }
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      v16 = 65;
      v17 = "Write failed!";
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_36;
      }
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      v16 = 64;
      v17 = "Read failed!";
    }
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v16,
      (unsigned int)&WPP_c4d247ff647635a25b2fe01fcd88288b_Traceguids,
      v15,
      (__int64)v17,
      v10);
    goto LABEL_36;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v14 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      63,
      (unsigned int)&WPP_c4d247ff647635a25b2fe01fcd88288b_Traceguids,
      v14,
      (__int64)"VOID[]");
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x14004a900  mov     rax, rsp
0x14004a903  mov     [rax+8], rbx
0x14004a907  mov     [rax+20h], rbp
0x14004a90b  mov     [rax+18h], r8
0x14004a90f  push    rsi
0x14004a910  push    rdi
0x14004a911  push    r14
0x14004a913  sub     rsp, 90h
0x14004a91a  mov     dword ptr [rax+10h], 0
0x14004a921  mov     rdi, r9
0x14004a924  mov     dword ptr [rax-78h], 0
0x14004a92b  mov     rbx, r8
0x14004a92e  mov     r14, rdx
0x14004a931  mov     rbp, rcx
0x14004a934  test    rdx, rdx
0x14004a937  jnz     short loc_14004A985
0x14004a939  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a940  lea     rax, WPP_GLOBAL_Control
0x14004a947  cmp     rcx, rax
0x14004a94a  jz      short loc_14004A97B
0x14004a94c  test    byte ptr [rcx+1Ch], 1
0x14004a950  jz      short loc_14004A97B
0x14004a952  cmp     byte ptr [rcx+19h], 2
0x14004a956  jb      short loc_14004A97B
0x14004a958  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004a95d  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a964  lea     edx, [r14+3Dh]
0x14004a968  mov     r9d, eax
0x14004a96b  lea     r8, WPP_c4d247ff647635a25b2fe01fcd88288b_Traceguids
0x14004a972  mov     rcx, [rcx+10h]
0x14004a976  call    WPP_SF_d
0x14004a97b  mov     ebx, 80030009h
0x14004a980  jmp     loc_14004AB9F
0x14004a985  or      eax, 0FFFFFFFFh
0x14004a988  cmp     ebx, eax
0x14004a98a  jnz     loc_14004AA2D
0x14004a990  cmp     [rsp+0A8h+arg_14], eax
0x14004a997  jnz     loc_14004AA2D
0x14004a99d  xor     edx, edx; Val
0x14004a99f  lea     rcx, [rsp+0A8h+var_68]; void *
0x14004a9a4  lea     r8d, [rdx+50h]; Size
0x14004a9a8  call    memset_0
0x14004a9ad  mov     r8d, 1; unsigned int
0x14004a9b3  lea     rdx, [rsp+0A8h+var_68]; struct tagSTATSTG *
0x14004a9b8  mov     rcx, rbp; this
0x14004a9bb  call    ?Stat@CProxyStream@@UEAAJPEAUtagSTATSTG@@K@Z; CProxyStream::Stat(tagSTATSTG *,ulong)
0x14004a9c0  mov     ebx, eax
0x14004a9c2  test    eax, eax
0x14004a9c4  jns     short loc_14004AA2A
0x14004a9c6  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a9cd  lea     rax, WPP_GLOBAL_Control
0x14004a9d4  cmp     rcx, rax
0x14004a9d7  jz      loc_14004AB9F
0x14004a9dd  test    byte ptr [rcx+1Ch], 8
0x14004a9e1  jz      loc_14004AB9F
0x14004a9e7  cmp     byte ptr [rcx+19h], 2
0x14004a9eb  jb      loc_14004AB9F
0x14004a9f1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004a9f6  lea     rcx, aStatFailed_0; "Stat failed!"
0x14004a9fd  mov     [rsp+0A8h+var_80], ebx
0x14004aa01  mov     [rsp+0A8h+var_88], rcx
0x14004aa06  lea     r8, WPP_c4d247ff647635a25b2fe01fcd88288b_Traceguids
0x14004aa0d  mov     rcx, cs:WPP_GLOBAL_Control
0x14004aa14  mov     edx, 3Eh ; '>'
0x14004aa19  mov     r9d, eax
0x14004aa1c  mov     rcx, [rcx+10h]
0x14004aa20  call    WPP_SF_DsD
0x14004aa25  jmp     loc_14004AB9F
0x14004aa2a  mov     ebx, [rbp+20h]
0x14004aa2d  mov     ecx, ebx
0x14004aa2f  call    PAL_System_MemAlloc
0x14004aa34  mov     rsi, rax
0x14004aa37  test    rax, rax
0x14004aa3a  jnz     short loc_14004AA93
0x14004aa3c  mov     rcx, cs:WPP_GLOBAL_Control
0x14004aa43  lea     rax, WPP_GLOBAL_Control
0x14004aa4a  cmp     rcx, rax
0x14004aa4d  jz      short loc_14004AA89
0x14004aa4f  test    byte ptr [rcx+1Ch], 8
0x14004aa53  jz      short loc_14004AA89
0x14004aa55  cmp     byte ptr [rcx+19h], 2
0x14004aa59  jb      short loc_14004AA89
0x14004aa5b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004aa60  lea     rcx, aVoid; "VOID[]"
0x14004aa67  mov     r9d, eax
0x14004aa6a  mov     [rsp+0A8h+var_88], rcx
0x14004aa6f  lea     edx, [rsi+3Fh]
0x14004aa72  mov     rcx, cs:WPP_GLOBAL_Control
0x14004aa79  lea     r8, WPP_c4d247ff647635a25b2fe01fcd88288b_Traceguids
0x14004aa80  mov     rcx, [rcx+10h]
0x14004aa84  call    WPP_SF_Ds
0x14004aa89  mov     ebx, 8007000Eh
0x14004aa8e  jmp     loc_14004AB9F
0x14004aa93  lea     r9, [rsp+0A8h+arg_8]; unsigned int *
0x14004aa9b  mov     r8d, ebx; Size
0x14004aa9e  mov     rdx, rsi; void *
0x14004aaa1  mov     rcx, rbp; this
0x14004aaa4  call    ?Read@CProxyStream@@UEAAJPEAXKPEAK@Z; CProxyStream::Read(void *,ulong,ulong *)
0x14004aaa9  mov     ebx, eax
0x14004aaab  test    eax, eax
0x14004aaad  jns     short loc_14004AB13
0x14004aaaf  mov     rcx, cs:WPP_GLOBAL_Control
0x14004aab6  lea     rax, WPP_GLOBAL_Control
0x14004aabd  cmp     rcx, rax
0x14004aac0  jz      loc_14004AB96
0x14004aac6  test    byte ptr [rcx+1Ch], 8
0x14004aaca  jz      loc_14004AB96
0x14004aad0  cmp     byte ptr [rcx+19h], 2
0x14004aad4  jb      loc_14004AB96
0x14004aada  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004aadf  mov     edx, 40h ; '@'
0x14004aae4  lea     rcx, aReadFailed; "Read failed!"
0x14004aaeb  mov     [rsp+0A8h+var_80], ebx
0x14004aaef  lea     r8, WPP_c4d247ff647635a25b2fe01fcd88288b_Traceguids
0x14004aaf6  mov     [rsp+0A8h+var_88], rcx
0x14004aafb  mov     r9d, eax
0x14004aafe  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ab05  mov     rcx, [rcx+10h]
0x14004ab09  call    WPP_SF_DsD
0x14004ab0e  jmp     loc_14004AB96
0x14004ab13  mov     r8d, [rsp+0A8h+arg_8]
0x14004ab1b  test    rdi, rdi
0x14004ab1e  jz      short loc_14004AB2A
0x14004ab20  mov     [rdi], r8d
0x14004ab23  mov     dword ptr [rdi+4], 0
0x14004ab2a  mov     rax, [r14]
0x14004ab2d  lea     r9, [rsp+0A8h+var_78]
0x14004ab32  mov     rdx, rsi
0x14004ab35  mov     rcx, r14
0x14004ab38  mov     rax, [rax+20h]
0x14004ab3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ab41  mov     ebx, eax
0x14004ab43  test    eax, eax
0x14004ab45  jns     short loc_14004AB7C
0x14004ab47  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ab4e  lea     rax, WPP_GLOBAL_Control
0x14004ab55  cmp     rcx, rax
0x14004ab58  jz      short loc_14004AB96
0x14004ab5a  test    byte ptr [rcx+1Ch], 8
0x14004ab5e  jz      short loc_14004AB96
0x14004ab60  cmp     byte ptr [rcx+19h], 2
0x14004ab64  jb      short loc_14004AB96
0x14004ab66  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004ab6b  mov     edx, 41h ; 'A'
0x14004ab70  lea     rcx, aWriteFailed; "Write failed!"
0x14004ab77  jmp     loc_14004AAEB
0x14004ab7c  mov     rcx, [rsp+0A8h+arg_20]
0x14004ab84  test    rcx, rcx
0x14004ab87  jz      short loc_14004AB96
0x14004ab89  mov     eax, [rsp+0A8h+var_78]
0x14004ab8d  mov     [rcx], eax
0x14004ab8f  mov     dword ptr [rcx+4], 0
0x14004ab96  mov     rcx, rsi; hMem
0x14004ab99  call    cs:__imp_LocalFree
0x14004ab9f  lea     r11, [rsp+0A8h+var_18]
0x14004aba7  mov     eax, ebx
0x14004aba9  mov     rbx, [r11+20h]
0x14004abad  mov     rbp, [r11+38h]
0x14004abb1  mov     rsp, r11
0x14004abb4  pop     r14
0x14004abb6  pop     rdi
0x14004abb7  pop     rsi
0x14004abb8  retn
```
