# CMSDiscMasterObj::CreateAudioTrack(long)

- ea: `0x18000a430`
- end: `0x18000a55e`
- name: `?CreateAudioTrack@CMSDiscMasterObj@@UEAAJJ@Z`
- size: `302`
- prototype: `__int64 __fastcall(CMSDiscMasterObj *this, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180007d40`
- `0x180007d80`
- `0x18000a430`
- `0x18000c69c`
- `0x180010aac`
- `0x180015260`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000a51a`
- `KERNEL32!LeaveCriticalSection` at `0x18000a51a`
- `KERNEL32!EnterCriticalSection` at `0x18000a494`
- `KERNEL32!EnterCriticalSection` at `0x18000a494`

## pseudocode

```c
__int64 __fastcall CMSDiscMasterObj::CreateAudioTrack(CMSDiscMasterObj *this, unsigned int a2)
{
  __int64 result; // rax
  int v5; // edi
  bool v6; // zf

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    WPP_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      20,
      WPP_9ba525f9c8053e0f887dcd9cfec1e277_Traceguids,
      (char *)this - 16);
  result = CMSDiscMasterObj::IsCallLegal((CMSDiscMasterObj *)((char *)this - 16), 0x15u);
  if ( (int)result >= 0 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 584));
    if ( *((_BYTE *)this + 552) )
    {
      v5 = -2147220965;
    }
    else if ( *((_DWORD *)this + 144) < 0x63u && *((_DWORD *)this + 141) )
    {
      v5 = CRedbookTracks::AddTrack((CMSDiscMasterObj *)((char *)this + 496), a2);
      if ( v5 >= 0 )
      {
        ++*((_DWORD *)this + 144);
        v6 = *((_DWORD *)this + 47) == 0;
        *((_BYTE *)this + 552) = 1;
        *((_DWORD *)this + 139) = a2;
        *((_DWORD *)this + 140) = 0;
        if ( !v6 )
        {
          *((_DWORD *)this + 69) |= 1u;
          *((_DWORD *)this + 62) = a2;
          *((_DWORD *)this + 63) = 0;
          *((_DWORD *)this + 75) = a2;
        }
        CMyUpdateList::UpdateAll((CMSDiscMasterObj *)((char *)this + 176));
      }
    }
    else
    {
      v5 = -2147220964;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 584));
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        21,
        WPP_9ba525f9c8053e0f887dcd9cfec1e277_Traceguids,
        (char *)this - 16,
        v5);
    return (unsigned int)v5;
  }
  return result;
}

```

## disassembly

```asm
0x18000a430  push    rbx
0x18000a432  push    rbp
0x18000a433  push    rsi
0x18000a434  push    rdi
0x18000a435  push    r12
0x18000a437  push    r14
0x18000a439  sub     rsp, 38h
0x18000a43d  mov     esi, edx
0x18000a43f  mov     rbx, rcx
0x18000a442  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a449  lea     r12, WPP_GLOBAL_Control
0x18000a450  cmp     rcx, r12
0x18000a453  jz      short loc_18000A474
0x18000a455  test    byte ptr [rcx+44h], 1
0x18000a459  jz      short loc_18000A474
0x18000a45b  mov     rcx, [rcx+38h]
0x18000a45f  lea     r9, [rbx-10h]
0x18000a463  mov     edx, 14h
0x18000a468  lea     r8, WPP_9ba525f9c8053e0f887dcd9cfec1e277_Traceguids
0x18000a46f  call    WPP_SF_q
0x18000a474  mov     edx, 15h; unsigned int
0x18000a479  lea     rcx, [rbx-10h]; this
0x18000a47d  call    ?IsCallLegal@CMSDiscMasterObj@@AEAAJK@Z; CMSDiscMasterObj::IsCallLegal(ulong)
0x18000a482  test    eax, eax
0x18000a484  js      loc_18000A551
0x18000a48a  lea     rbp, [rbx+248h]
0x18000a491  mov     rcx, rbp; lpCriticalSection
0x18000a494  call    cs:__imp_EnterCriticalSection
0x18000a49a  cmp     byte ptr [rbx+228h], 0
0x18000a4a1  jz      short loc_18000A4AA
0x18000a4a3  mov     edi, 8004021Bh
0x18000a4a8  jmp     short loc_18000A517
0x18000a4aa  cmp     dword ptr [rbx+240h], 63h ; 'c'
0x18000a4b1  jnb     short loc_18000A512
0x18000a4b3  cmp     dword ptr [rbx+234h], 0
0x18000a4ba  jz      short loc_18000A512
0x18000a4bc  lea     rcx, [rbx+1F0h]; this
0x18000a4c3  mov     edx, esi; unsigned int
0x18000a4c5  call    ?AddTrack@CRedbookTracks@@QEAAJK@Z; CRedbookTracks::AddTrack(ulong)
0x18000a4ca  mov     edi, eax
0x18000a4cc  test    eax, eax
0x18000a4ce  js      short loc_18000A517
0x18000a4d0  inc     dword ptr [rbx+240h]
0x18000a4d6  lea     rcx, [rbx+0B0h]; this
0x18000a4dd  cmp     dword ptr [rcx+0Ch], 0
0x18000a4e1  mov     byte ptr [rbx+228h], 1
0x18000a4e8  mov     [rbx+22Ch], esi
0x18000a4ee  mov     dword ptr [rbx+230h], 0
0x18000a4f8  jz      short loc_18000A50B
0x18000a4fa  or      dword ptr [rcx+64h], 1
0x18000a4fe  mov     [rcx+48h], esi
0x18000a501  mov     dword ptr [rcx+4Ch], 0
0x18000a508  mov     [rcx+7Ch], esi
0x18000a50b  call    ?UpdateAll@CMyUpdateList@@QEAAXXZ; CMyUpdateList::UpdateAll(void)
0x18000a510  jmp     short loc_18000A517
0x18000a512  mov     edi, 8004021Ch
0x18000a517  mov     rcx, rbp; lpCriticalSection
0x18000a51a  call    cs:__imp_LeaveCriticalSection
0x18000a520  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a527  cmp     rcx, r12
0x18000a52a  jz      short loc_18000A54F
0x18000a52c  test    byte ptr [rcx+44h], 1
0x18000a530  jz      short loc_18000A54F
0x18000a532  mov     rcx, [rcx+38h]
0x18000a536  lea     r9, [rbx-10h]
0x18000a53a  mov     edx, 15h
0x18000a53f  mov     [rsp+68h+var_48], edi
0x18000a543  lea     r8, WPP_9ba525f9c8053e0f887dcd9cfec1e277_Traceguids
0x18000a54a  call    WPP_SF_qD
0x18000a54f  mov     eax, edi
0x18000a551  add     rsp, 38h
0x18000a555  pop     r14
0x18000a557  pop     r12
0x18000a559  pop     rdi
0x18000a55a  pop     rsi
0x18000a55b  pop     rbp
0x18000a55c  pop     rbx
0x18000a55d  retn
```
