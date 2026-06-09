# CRdpWindowTracker::GetWindowState(unsigned __int64,RDP_WINDOW_STATE *)

- ea: `0x14005cdf0`
- end: `0x14005d02e`
- name: `?GetWindowState@CRdpWindowTracker@@UEAAJ_KPEAURDP_WINDOW_STATE@@@Z`
- size: `574`
- prototype: `int(CRdpWindowTracker *__hidden this, unsigned __int64, struct RDP_WINDOW_STATE *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14005d040`

## callees

- `0x140004b1c`
- `0x140005750`
- `0x14000d350`
- `0x14000efb8`
- `0x140011054`
- `0x14005ba0c`
- `0x14005c5dc`
- `0x14005cdf0`

## import_xrefs

- `USER32!CopyRect` at `0x14005cf87`
- `USER32!CopyRect` at `0x14005cf95`
- `USER32!CopyRect` at `0x14005cfa3`
- `USER32!CopyRect` at `0x14005cf87`
- `USER32!CopyRect` at `0x14005cf95`
- `USER32!CopyRect` at `0x14005cfa3`

## pseudocode

```c
__int64 __fastcall CRdpWindowTracker::GetWindowState(CRdpWindowTracker *this, HWND a2, struct RDP_WINDOW_STATE *a3)
{
  CRdpWindowTracker *v3; // rsi
  int v6; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  struct RDP_TRACKED_WINDOW_NODE *v10; // rbx
  const RECT *v11; // rdx
  unsigned int v12; // eax
  char *v14; // [rsp+40h] [rbp+8h] BYREF
  struct RDP_TRACKED_WINDOW_NODE *v15; // [rsp+48h] [rbp+10h] BYREF

  v3 = (CRdpWindowTracker *)((char *)this - 48);
  if ( ((unsigned __int64)a2 & *((_QWORD *)this + 28)) != 0 )
  {
    v6 = -2147467259;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        28,
        (unsigned int)&WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"ValidateHWND() failed.  The parameter hWnd does not match the current system architecture (32/64 bit)",
        -2147467259);
    }
  }
  else if ( a3 )
  {
    v15 = 0;
    v14 = (char *)this + 8;
    CTSCriticalSection::Lock((CRdpWindowTracker *)((char *)this + 8));
    if ( (unsigned int)CRdpWindowTracker::GetNodeFromHWND(v3, a2, &v15) )
    {
      v10 = v15;
      v11 = (const RECT *)((char *)v15 + 44);
      *(_DWORD *)a3 = *((_DWORD *)v15 + 10);
      *((_QWORD *)a3 + 1) = *((_QWORD *)v10 + 2);
      *((_QWORD *)a3 + 2) = *((_QWORD *)v10 + 3);
      *((_QWORD *)a3 + 3) = *((_QWORD *)v10 + 4);
      *((_DWORD *)a3 + 282) = *((_DWORD *)v10 + 26);
      CopyRect((LPRECT)a3 + 2, v11);
      CopyRect((LPRECT)a3 + 3, (const RECT *)((char *)v10 + 60));
      CopyRect((LPRECT)a3 + 4, (const RECT *)((char *)v10 + 76));
      v6 = CRdpWindowTracker::ConvertHrgnToRdpRegionUsingBuffer(
             v3,
             *((HRGN *)v10 + 12),
             (struct RDP_WINDOW_STATE *)((char *)a3 + 80));
      if ( v6 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v12 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          31,
          (unsigned int)&WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids,
          v12,
          (__int64)"ConvertHrgnToRdpRegionUsingBuffer() failed",
          v6);
      }
    }
    else
    {
      v6 = -2147023496;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v9 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          30,
          (unsigned int)&WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids,
          v9,
          (__int64)"GetNodeFromHWND() failed",
          -2147023496);
      }
    }
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v14);
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        (unsigned int)&WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids,
        v8,
        (__int64)"pWindowState");
    }
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14005cdf0  mov     [rsp+arg_10], rbx
0x14005cdf5  mov     [rsp+arg_18], rsi
0x14005cdfa  push    rdi
0x14005cdfb  sub     rsp, 30h
0x14005cdff  lea     rsi, [rcx-30h]
0x14005ce03  mov     rdi, r8
0x14005ce06  mov     rbx, rdx
0x14005ce09  test    [rsi+110h], rdx
0x14005ce10  jz      short loc_14005CE7F
0x14005ce12  mov     ebx, 80004005h
0x14005ce17  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ce1e  lea     rax, WPP_GLOBAL_Control
0x14005ce25  cmp     rcx, rax
0x14005ce28  jz      loc_14005D01C
0x14005ce2e  test    byte ptr [rcx+1Ch], 8
0x14005ce32  jz      loc_14005D01C
0x14005ce38  cmp     byte ptr [rcx+19h], 2
0x14005ce3c  jb      loc_14005D01C
0x14005ce42  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005ce47  lea     rcx, aValidatehwndFa; "ValidateHWND() failed.  The parameter h"...
0x14005ce4e  mov     [rsp+38h+var_10], 80004005h
0x14005ce56  mov     [rsp+38h+var_18], rcx
0x14005ce5b  lea     r8, WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids
0x14005ce62  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ce69  mov     edx, 1Ch
0x14005ce6e  mov     r9d, eax
0x14005ce71  mov     rcx, [rcx+10h]
0x14005ce75  call    WPP_SF_DsD
0x14005ce7a  jmp     loc_14005D01C
0x14005ce7f  test    rdi, rdi
0x14005ce82  jnz     short loc_14005CEDB
0x14005ce84  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ce8b  lea     rax, WPP_GLOBAL_Control
0x14005ce92  cmp     rcx, rax
0x14005ce95  jz      short loc_14005CED1
0x14005ce97  test    byte ptr [rcx+1Ch], 8
0x14005ce9b  jz      short loc_14005CED1
0x14005ce9d  cmp     byte ptr [rcx+19h], 2
0x14005cea1  jb      short loc_14005CED1
0x14005cea3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005cea8  lea     rcx, aPwindowstate; "pWindowState"
0x14005ceaf  mov     r9d, eax
0x14005ceb2  mov     [rsp+38h+var_18], rcx
0x14005ceb7  lea     edx, [rdi+1Dh]
0x14005ceba  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cec1  lea     r8, WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids
0x14005cec8  mov     rcx, [rcx+10h]
0x14005cecc  call    WPP_SF_Ds
0x14005ced1  mov     ebx, 80004003h
0x14005ced6  jmp     loc_14005D01C
0x14005cedb  add     rcx, 8; this
0x14005cedf  mov     [rsp+38h+arg_8], 0
0x14005cee8  mov     [rsp+38h+arg_0], rcx
0x14005ceed  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x14005cef2  lea     r8, [rsp+38h+arg_8]; struct RDP_TRACKED_WINDOW_NODE **
0x14005cef7  mov     rdx, rbx; HWND
0x14005cefa  mov     rcx, rsi; this
0x14005cefd  call    ?GetNodeFromHWND@CRdpWindowTracker@@AEAAHPEAUHWND__@@PEAPEAURDP_TRACKED_WINDOW_NODE@@@Z; CRdpWindowTracker::GetNodeFromHWND(HWND__ *,RDP_TRACKED_WINDOW_NODE * *)
0x14005cf02  test    eax, eax
0x14005cf04  jnz     short loc_14005CF54
0x14005cf06  mov     ebx, 80070578h
0x14005cf0b  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cf12  lea     rax, WPP_GLOBAL_Control
0x14005cf19  cmp     rcx, rax
0x14005cf1c  jz      loc_14005D012
0x14005cf22  test    byte ptr [rcx+1Ch], 8
0x14005cf26  jz      loc_14005D012
0x14005cf2c  cmp     byte ptr [rcx+19h], 2
0x14005cf30  jb      loc_14005D012
0x14005cf36  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005cf3b  mov     edx, 1Eh
0x14005cf40  mov     [rsp+38h+var_10], 80070578h
0x14005cf48  lea     rcx, aGetnodefromhwn; "GetNodeFromHWND() failed"
0x14005cf4f  jmp     loc_14005CFF3
0x14005cf54  mov     rbx, [rsp+38h+arg_8]
0x14005cf59  lea     rcx, [rdi+20h]; lprcDst
0x14005cf5d  mov     eax, [rbx+28h]
0x14005cf60  lea     rdx, [rbx+2Ch]; lprcSrc
0x14005cf64  mov     [rdi], eax
0x14005cf66  mov     rax, [rbx+10h]
0x14005cf6a  mov     [rdi+8], rax
0x14005cf6e  mov     rax, [rbx+18h]
0x14005cf72  mov     [rdi+10h], rax
0x14005cf76  mov     rax, [rbx+20h]
0x14005cf7a  mov     [rdi+18h], rax
0x14005cf7e  mov     eax, [rbx+68h]
0x14005cf81  mov     [rdi+468h], eax
0x14005cf87  call    cs:__imp_CopyRect
0x14005cf8d  lea     rdx, [rbx+3Ch]; lprcSrc
0x14005cf91  lea     rcx, [rdi+30h]; lprcDst
0x14005cf95  call    cs:__imp_CopyRect
0x14005cf9b  lea     rdx, [rbx+4Ch]; lprcSrc
0x14005cf9f  lea     rcx, [rdi+40h]; lprcDst
0x14005cfa3  call    cs:__imp_CopyRect
0x14005cfa9  mov     rdx, [rbx+60h]; HRGN
0x14005cfad  lea     r8, [rdi+50h]; struct _RDPGFX_REGION *
0x14005cfb1  mov     rcx, rsi; this
0x14005cfb4  call    ?ConvertHrgnToRdpRegionUsingBuffer@CRdpWindowTracker@@AEAAJPEAUHRGN__@@PEAU_RDPGFX_REGION@@@Z; CRdpWindowTracker::ConvertHrgnToRdpRegionUsingBuffer(HRGN__ *,_RDPGFX_REGION *)
0x14005cfb9  mov     ebx, eax
0x14005cfbb  test    eax, eax
0x14005cfbd  jns     short loc_14005D012
0x14005cfbf  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cfc6  lea     rax, WPP_GLOBAL_Control
0x14005cfcd  cmp     rcx, rax
0x14005cfd0  jz      short loc_14005D012
0x14005cfd2  test    byte ptr [rcx+1Ch], 8
0x14005cfd6  jz      short loc_14005D012
0x14005cfd8  cmp     byte ptr [rcx+19h], 2
0x14005cfdc  jb      short loc_14005D012
0x14005cfde  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005cfe3  mov     edx, 1Fh
0x14005cfe8  mov     [rsp+38h+var_10], ebx
0x14005cfec  lea     rcx, aConverthrgntor; "ConvertHrgnToRdpRegionUsingBuffer() fai"...
0x14005cff3  mov     [rsp+38h+var_18], rcx
0x14005cff8  lea     r8, WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids
0x14005cfff  mov     rcx, cs:WPP_GLOBAL_Control
0x14005d006  mov     r9d, eax
0x14005d009  mov     rcx, [rcx+10h]
0x14005d00d  call    WPP_SF_DsD
0x14005d012  lea     rcx, [rsp+38h+arg_0]; this
0x14005d017  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x14005d01c  mov     rsi, [rsp+38h+arg_18]
0x14005d021  mov     eax, ebx
0x14005d023  mov     rbx, [rsp+38h+arg_10]
0x14005d028  add     rsp, 30h
0x14005d02c  pop     rdi
0x14005d02d  retn
```
