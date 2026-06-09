# EapHost::Peer::PeerProxy::FindAndReplace(EapHost::Peer::ConnectionSessionInfo *)

- ea: `0x18000bd30`
- end: `0x18000beeb`
- name: `?FindAndReplace@PeerProxy@Peer@EapHost@@QEAAKPEAVConnectionSessionInfo@23@@Z`
- size: `443`
- prototype: `unsigned int __fastcall(EapHost::Peer::PeerProxy *__hidden this, struct EapHost::Peer::ConnectionSessionInfo *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000b8bc`

## callees

- `0x180001780`
- `0x18000ace0`
- `0x18000adb4`
- `0x18000b1b0`
- `0x18000bd30`
- `0x18000c6e0`
- `0x18000ca10`
- `0x18000cdfc`
- `0x18000ce34`

## pseudocode

```c
__int64 __fastcall EapHost::Peer::PeerProxy::FindAndReplace(
        EapHost::Peer::PeerProxy *this,
        struct EapHost::Peer::ConnectionSessionInfo *a2)
{
  unsigned int v3; // r14d
  __int64 v4; // r8
  _QWORD *i; // rbx
  __int64 v6; // rcx
  volatile signed __int32 *v7; // rdi
  __int64 v8; // rax
  const wchar_t *v9; // rcx
  int v10; // eax
  volatile signed __int32 v12; // [rsp+30h] [rbp-39h] BYREF
  __int64 v13; // [rsp+38h] [rbp-31h] BYREF
  int v14; // [rsp+40h] [rbp-29h]
  char v15[16]; // [rsp+48h] [rbp-21h] BYREF
  const wchar_t *v16; // [rsp+58h] [rbp-11h]
  int v17; // [rsp+60h] [rbp-9h]
  int v18; // [rsp+64h] [rbp-5h]
  volatile signed __int32 *v19; // [rsp+68h] [rbp-1h]
  __int64 v20; // [rsp+70h] [rbp+7h]

  v13 = 0;
  v14 = 0;
  v3 = 1168;
  EapNs::EapCriticalSection::AttachAndEnter((EapNs::EapCriticalSection *)&v13, &CriticalSection);
  for ( i = *(_QWORD **)peerProxy; i != (_QWORD *)peerProxy; i = (_QWORD *)*i )
  {
    v6 = i[2];
    if ( *(_QWORD *)((char *)a2 + 4) == *(_QWORD *)(v6 + 4) && *(_QWORD *)((char *)a2 + 12) == *(_QWORD *)(v6 + 12) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_a2bbe9c3264d3ee44dc19a0825749d97_Traceguids);
      v7 = (volatile signed __int32 *)i[2];
      if ( _InterlockedCompareExchange(v7 + 43, 1, 0) )
      {
        v3 = 1237;
        if ( (Microsoft_Windows_EapHostEnableBits & 0x20) != 0 )
        {
          v12 = *v7;
          if ( v7 == (volatile signed __int32 *)-20LL )
          {
            v9 = L"NULL";
            v10 = 10;
          }
          else
          {
            v8 = -1;
            do
              ++v8;
            while ( *((_WORD *)v7 + v8 + 10) );
            v9 = (const wchar_t *)(v7 + 5);
            v10 = 2 * v8 + 2;
          }
          v17 = v10;
          v16 = v9;
          v19 = &v12;
          v18 = 0;
          v20 = 4;
          McGenEventWrite_EtwEventWriteTransfer(
            &eaphost_Context,
            (__int64)PeerSessionRequestForActiveSession,
            v4,
            3,
            (__int64)v15);
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            16,
            (unsigned int)WPP_a2bbe9c3264d3ee44dc19a0825749d97_Traceguids,
            (_DWORD)v7 + 20,
            *v7);
      }
      else
      {
        v3 = 0;
        EapHost::Peer::ConnectionSessionInfo::StopListeningThread((EapHost::Peer::ConnectionSessionInfo *)v7, 0);
        EapHost::Peer::ConnectionSessionInfo::ReduceRefCount((EapHost::Peer::ConnectionSessionInfo *)v7);
        i[2] = a2;
      }
      break;
    }
  }
  EapNs::EapCriticalSection::~EapCriticalSection((EapNs::EapCriticalSection *)&v13);
  return v3;
}

```

## disassembly

```asm
0x18000bd30  push    rbp
0x18000bd32  push    rbx
0x18000bd33  push    rsi
0x18000bd34  push    rdi
0x18000bd35  push    r12
0x18000bd37  push    r13
0x18000bd39  push    r14
0x18000bd3b  push    r15
0x18000bd3d  lea     rbp, [rsp-1Fh]
0x18000bd42  sub     rsp, 88h
0x18000bd49  mov     rax, cs:__security_cookie
0x18000bd50  xor     rax, rsp
0x18000bd53  mov     [rbp+57h+var_48], rax
0x18000bd57  xor     r15d, r15d
0x18000bd5a  lea     rcx, [rbp+57h+var_88]; this
0x18000bd5e  mov     rsi, rdx
0x18000bd61  mov     [rbp+57h+var_88], r15
0x18000bd65  lea     rdx, CriticalSection; struct _RTL_CRITICAL_SECTION *
0x18000bd6c  mov     [rbp+57h+var_80], r15d
0x18000bd70  mov     r14d, 490h
0x18000bd76  call    ?AttachAndEnter@EapCriticalSection@EapNs@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; EapNs::EapCriticalSection::AttachAndEnter(_RTL_CRITICAL_SECTION *)
0x18000bd7b  mov     rdx, cs:?peerProxy@@3VPeerProxy@Peer@EapHost@@A; EapHost::Peer::PeerProxy peerProxy
0x18000bd82  mov     rbx, [rdx]
0x18000bd85  cmp     rbx, rdx
0x18000bd88  jz      loc_18000BEBE
0x18000bd8e  mov     rcx, [rbx+10h]
0x18000bd92  mov     rax, [rsi+4]
0x18000bd96  cmp     rax, [rcx+4]
0x18000bd9a  jnz     short loc_18000BDA6
0x18000bd9c  mov     rax, [rsi+0Ch]
0x18000bda0  cmp     rax, [rcx+0Ch]
0x18000bda4  jz      short loc_18000BDAB
0x18000bda6  mov     rbx, [rbx]
0x18000bda9  jmp     short loc_18000BD85
0x18000bdab  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bdb2  lea     r12, WPP_GLOBAL_Control
0x18000bdb9  cmp     rcx, r12
0x18000bdbc  jz      short loc_18000BDD9
0x18000bdbe  test    byte ptr [rcx+1Ch], 4
0x18000bdc2  jz      short loc_18000BDD9
0x18000bdc4  mov     rcx, [rcx+10h]
0x18000bdc8  lea     r8, WPP_a2bbe9c3264d3ee44dc19a0825749d97_Traceguids
0x18000bdcf  mov     edx, 0Fh
0x18000bdd4  call    WPP_SF_
0x18000bdd9  mov     rdi, [rbx+10h]
0x18000bddd  xor     eax, eax
0x18000bddf  lea     r13d, [rax+1]
0x18000bde3  lock cmpxchg [rdi+0ACh], r13d
0x18000bdec  jnz     short loc_18000BE0C
0x18000bdee  xor     edx, edx; bool
0x18000bdf0  mov     rcx, rdi; this
0x18000bdf3  mov     r14d, r15d
0x18000bdf6  call    ?StopListeningThread@ConnectionSessionInfo@Peer@EapHost@@QEAAX_N@Z; EapHost::Peer::ConnectionSessionInfo::StopListeningThread(bool)
0x18000bdfb  mov     rcx, rdi; this
0x18000bdfe  call    ?ReduceRefCount@ConnectionSessionInfo@Peer@EapHost@@QEAAXXZ; EapHost::Peer::ConnectionSessionInfo::ReduceRefCount(void)
0x18000be03  mov     [rbx+10h], rsi
0x18000be07  jmp     loc_18000BEBE
0x18000be0c  test    cs:Microsoft_Windows_EapHostEnableBits, 20h
0x18000be13  lea     rbx, [rdi+14h]
0x18000be17  mov     r14d, 4D5h
0x18000be1d  jz      short loc_18000BE8C
0x18000be1f  mov     eax, [rdi]
0x18000be21  mov     [rbp+57h+var_90], eax
0x18000be24  test    rbx, rbx
0x18000be27  jz      short loc_18000BE43
0x18000be29  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000be2d  inc     rax
0x18000be30  cmp     [rbx+rax*2], r15w
0x18000be35  jnz     short loc_18000BE2D
0x18000be37  mov     rcx, rbx
0x18000be3a  lea     eax, ds:2[rax*2]
0x18000be41  jmp     short loc_18000BE4F
0x18000be43  lea     rcx, aNull; "NULL"
0x18000be4a  mov     eax, 0Ah
0x18000be4f  mov     [rbp+57h+var_60], eax
0x18000be52  lea     rdx, PeerSessionRequestForActiveSession
0x18000be59  lea     rax, [rbp+57h+var_90]
0x18000be5d  mov     [rbp+57h+var_68], rcx
0x18000be61  mov     [rbp+57h+var_58], rax
0x18000be65  lea     rcx, eaphost_Context
0x18000be6c  lea     rax, [rbp+57h+var_78]
0x18000be70  mov     [rbp+57h+var_5C], r15d
0x18000be74  mov     r9d, 3
0x18000be7a  mov     [rsp+0C0h+var_A0], rax
0x18000be7f  mov     [rbp+57h+var_50], 4
0x18000be87  call    McGenEventWrite_EtwEventWriteTransfer
0x18000be8c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000be93  cmp     rcx, r12
0x18000be96  jz      short loc_18000BEBE
0x18000be98  test    [rcx+1Ch], r13b
0x18000be9c  jz      short loc_18000BEBE
0x18000be9e  mov     r10d, [rdi]
0x18000bea1  lea     r8, WPP_a2bbe9c3264d3ee44dc19a0825749d97_Traceguids
0x18000bea8  mov     rcx, [rcx+10h]
0x18000beac  mov     edx, 10h
0x18000beb1  mov     r9, rbx
0x18000beb4  mov     dword ptr [rsp+0C0h+var_A0], r10d
0x18000beb9  call    WPP_SF_Sd
0x18000bebe  lea     rcx, [rbp+57h+var_88]; this
0x18000bec2  call    ??1EapCriticalSection@EapNs@@QEAA@XZ; EapNs::EapCriticalSection::~EapCriticalSection(void)
0x18000bec7  mov     eax, r14d
0x18000beca  mov     rcx, [rbp+57h+var_48]
0x18000bece  xor     rcx, rsp; StackCookie
0x18000bed1  call    __security_check_cookie
0x18000bed6  add     rsp, 88h
0x18000bedd  pop     r15
0x18000bedf  pop     r14
0x18000bee1  pop     r13
0x18000bee3  pop     r12
0x18000bee5  pop     rdi
0x18000bee6  pop     rsi
0x18000bee7  pop     rbx
0x18000bee8  pop     rbp
0x18000bee9  retn
```
