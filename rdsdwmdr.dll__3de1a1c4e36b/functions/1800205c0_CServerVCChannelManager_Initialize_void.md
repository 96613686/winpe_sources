# CServerVCChannelManager::Initialize(void)

- ea: `0x1800205c0`
- end: `0x180020634`
- name: `?Initialize@CServerVCChannelManager@@UEAAJXZ`
- size: `116`
- prototype: `__int64 __fastcall(CServerVCChannelManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001fb94`

## callees

- `0x18001d114`
- `0x18001ef44`
- `0x18001f870`
- `0x1800205c0`

## string_xrefs

- `0x1800205fd`: `CAPCThread::CreateInstance FAILED`

## pseudocode

```c
__int64 __fastcall CServerVCChannelManager::Initialize(CServerVCChannelManager *this)
{
  int Instance; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v4; // [rsp+28h] [rbp-10h]

  *((_DWORD *)this + 5) |= 2u;
  Instance = CAPCThread::CreateInstance((struct IAPCThread **)this + 5);
  if ( Instance < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v4 = Instance;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      36,
      (unsigned int)&WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)"CAPCThread::CreateInstance FAILED",
      v4);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800205c0  push    rbx
0x1800205c2  sub     rsp, 30h
0x1800205c6  or      dword ptr [rcx+14h], 2
0x1800205ca  add     rcx, 28h ; '('; struct IAPCThread **
0x1800205ce  call    ?CreateInstance@CAPCThread@@SAJPEAPEAVIAPCThread@@@Z; CAPCThread::CreateInstance(IAPCThread * *)
0x1800205d3  mov     ebx, eax
0x1800205d5  test    eax, eax
0x1800205d7  jns     short loc_18002062C
0x1800205d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800205e0  lea     rax, WPP_GLOBAL_Control
0x1800205e7  cmp     rcx, rax
0x1800205ea  jz      short loc_18002062C
0x1800205ec  test    byte ptr [rcx+1Ch], 8
0x1800205f0  jz      short loc_18002062C
0x1800205f2  cmp     byte ptr [rcx+19h], 2
0x1800205f6  jb      short loc_18002062C
0x1800205f8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800205fd  lea     rcx, aCapcthreadCrea; "CAPCThread::CreateInstance FAILED"
0x180020604  mov     [rsp+38h+var_10], ebx
0x180020608  mov     [rsp+38h+var_18], rcx
0x18002060d  lea     r8, WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids
0x180020614  mov     rcx, cs:WPP_GLOBAL_Control
0x18002061b  mov     edx, 24h ; '$'
0x180020620  mov     r9d, eax
0x180020623  mov     rcx, [rcx+10h]
0x180020627  call    WPP_SF_DsD
0x18002062c  mov     eax, ebx
0x18002062e  add     rsp, 30h
0x180020632  pop     rbx
0x180020633  retn
```
