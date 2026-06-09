# CClipServer::RemoveNotificationSinks(void)

- ea: `0x14003de20`
- end: `0x14003e12d`
- name: `?RemoveNotificationSinks@CClipServer@@EEAAJXZ`
- size: `781`
- prototype: `__int64 __fastcall(CClipServer *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x140004b1c`
- `0x140005750`
- `0x14003de20`
- `0x140055100`
- `0x14006b010`

## string_xrefs

- `0x14003de7e`: `Failed to remove CLIP_CAPS event sink!`
- `0x14003deeb`: `Failed to remove TEMP_DIRECTORY event sink!`
- `0x14003df58`: `Failed to remove DATA_CHANNEL_REQUEST event sink!`
- `0x14003dfc5`: `Failed to remove DATA_CHANNEL_RESPONSE event sink!`
- `0x14003e032`: `Failed to remove DATA_CHANNEL_ACCEPTED event sink!`
- `0x14003e09f`: `Failed to remove FORMAT_LIST event sink!`
- `0x14003e0f5`: `CClipBase::RemoveNotificationSinks failed!`

## pseudocode

```c
__int64 __fastcall CClipServer::RemoveNotificationSinks(CClipServer *this)
{
  int v2; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v4; // edi
  unsigned int v5; // eax
  int v6; // edi
  unsigned int v7; // eax
  int v8; // edi
  unsigned int v9; // eax
  int v10; // edi
  unsigned int v11; // eax
  int v12; // edi
  unsigned int v13; // eax
  int v14; // ebx
  unsigned int v15; // eax
  __int64 v17; // [rsp+28h] [rbp-30h]
  int v18; // [rsp+28h] [rbp-30h]

  v2 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(**((_QWORD **)this + 85) + 96LL))(
         *((_QWORD *)this + 85),
         161,
         (char *)this + 864);
  if ( v2 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v18 = v2;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      53,
      (unsigned int)WPP_bda84ad720bd303d3567a2435a9ed67b_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)"Failed to remove CLIP_CAPS event sink!",
      v18);
  }
  v4 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(**((_QWORD **)this + 85) + 96LL))(
         *((_QWORD *)this + 85),
         162,
         (char *)this + 872);
  if ( v4 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v5 = RdpWppGetCurrentThreadActivityIdPrefix();
    LODWORD(v17) = v4;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      54,
      (unsigned int)WPP_bda84ad720bd303d3567a2435a9ed67b_Traceguids,
      v5,
      (__int64)"Failed to remove TEMP_DIRECTORY event sink!",
      v17);
  }
  v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(**((_QWORD **)this + 85) + 96LL))(
         *((_QWORD *)this + 85),
         170,
         (char *)this + 888);
  if ( v6 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v7 = RdpWppGetCurrentThreadActivityIdPrefix();
    LODWORD(v17) = v6;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      55,
      (unsigned int)WPP_bda84ad720bd303d3567a2435a9ed67b_Traceguids,
      v7,
      (__int64)"Failed to remove DATA_CHANNEL_REQUEST event sink!",
      v17);
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(**((_QWORD **)this + 85) + 96LL))(
         *((_QWORD *)this + 85),
         171,
         (char *)this + 896);
  if ( v8 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v9 = RdpWppGetCurrentThreadActivityIdPrefix();
    LODWORD(v17) = v8;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      56,
      (unsigned int)WPP_bda84ad720bd303d3567a2435a9ed67b_Traceguids,
      v9,
      (__int64)"Failed to remove DATA_CHANNEL_RESPONSE event sink!",
      v17);
  }
  v10 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(**((_QWORD **)this + 85) + 96LL))(
          *((_QWORD *)this + 85),
          173,
          (char *)this + 904);
  if ( v10 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v11 = RdpWppGetCurrentThreadActivityIdPrefix();
    LODWORD(v17) = v10;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      57,
      (unsigned int)WPP_bda84ad720bd303d3567a2435a9ed67b_Traceguids,
      v11,
      (__int64)"Failed to remove DATA_CHANNEL_ACCEPTED event sink!",
      v17);
  }
  v12 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(**((_QWORD **)this + 85) + 96LL))(
          *((_QWORD *)this + 85),
          155,
          (char *)this + 880);
  if ( v12 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v13 = RdpWppGetCurrentThreadActivityIdPrefix();
    LODWORD(v17) = v12;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      58,
      (unsigned int)WPP_bda84ad720bd303d3567a2435a9ed67b_Traceguids,
      v13,
      (__int64)"Failed to remove FORMAT_LIST event sink!",
      v17);
  }
  v14 = CClipBase::RemoveNotificationSinks(this);
  if ( v14 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v15 = RdpWppGetCurrentThreadActivityIdPrefix();
    LODWORD(v17) = v14;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      59,
      (unsigned int)WPP_bda84ad720bd303d3567a2435a9ed67b_Traceguids,
      v15,
      (__int64)"CClipBase::RemoveNotificationSinks failed!",
      v17);
  }
  return 0;
}

```

## disassembly

```asm
0x14003de20  push    rbx
0x14003de22  push    rdi
0x14003de23  push    r14
0x14003de25  push    r15
0x14003de27  sub     rsp, 38h
0x14003de2b  mov     rbx, rcx
0x14003de2e  mov     edx, 0A1h
0x14003de33  mov     rcx, [rcx+2A8h]
0x14003de3a  lea     r8, [rbx+360h]
0x14003de41  mov     rax, [rcx]
0x14003de44  mov     rax, [rax+60h]
0x14003de48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003de4d  lea     r15, WPP_bda84ad720bd303d3567a2435a9ed67b_Traceguids
0x14003de54  mov     edi, eax
0x14003de56  lea     r14, WPP_GLOBAL_Control
0x14003de5d  test    eax, eax
0x14003de5f  jns     short loc_14003DEA9
0x14003de61  mov     rcx, cs:WPP_GLOBAL_Control
0x14003de68  cmp     rcx, r14
0x14003de6b  jz      short loc_14003DEA9
0x14003de6d  test    byte ptr [rcx+1Ch], 8
0x14003de71  jz      short loc_14003DEA9
0x14003de73  cmp     byte ptr [rcx+19h], 2
0x14003de77  jb      short loc_14003DEA9
0x14003de79  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003de7e  lea     rcx, aFailedToRemove_12; "Failed to remove CLIP_CAPS event sink!"
0x14003de85  mov     dword ptr [rsp+58h+var_30], edi
0x14003de89  mov     [rsp+58h+var_38], rcx
0x14003de8e  mov     edx, 35h ; '5'
0x14003de93  mov     rcx, cs:WPP_GLOBAL_Control
0x14003de9a  mov     r9d, eax
0x14003de9d  mov     r8, r15
0x14003dea0  mov     rcx, [rcx+10h]
0x14003dea4  call    WPP_SF_DsD
0x14003dea9  mov     rcx, [rbx+2A8h]
0x14003deb0  lea     r8, [rbx+368h]
0x14003deb7  mov     edx, 0A2h
0x14003debc  mov     rax, [rcx]
0x14003debf  mov     rax, [rax+60h]
0x14003dec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003dec8  mov     edi, eax
0x14003deca  test    eax, eax
0x14003decc  jns     short loc_14003DF16
0x14003dece  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ded5  cmp     rcx, r14
0x14003ded8  jz      short loc_14003DF16
0x14003deda  test    byte ptr [rcx+1Ch], 8
0x14003dede  jz      short loc_14003DF16
0x14003dee0  cmp     byte ptr [rcx+19h], 2
0x14003dee4  jb      short loc_14003DF16
0x14003dee6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003deeb  lea     rcx, aFailedToRemove_18; "Failed to remove TEMP_DIRECTORY event s"...
0x14003def2  mov     dword ptr [rsp+58h+var_30], edi
0x14003def6  mov     [rsp+58h+var_38], rcx
0x14003defb  mov     edx, 36h ; '6'
0x14003df00  mov     rcx, cs:WPP_GLOBAL_Control
0x14003df07  mov     r9d, eax
0x14003df0a  mov     r8, r15
0x14003df0d  mov     rcx, [rcx+10h]
0x14003df11  call    WPP_SF_DsD
0x14003df16  mov     rcx, [rbx+2A8h]
0x14003df1d  lea     r8, [rbx+378h]
0x14003df24  mov     edx, 0AAh
0x14003df29  mov     rax, [rcx]
0x14003df2c  mov     rax, [rax+60h]
0x14003df30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003df35  mov     edi, eax
0x14003df37  test    eax, eax
0x14003df39  jns     short loc_14003DF83
0x14003df3b  mov     rcx, cs:WPP_GLOBAL_Control
0x14003df42  cmp     rcx, r14
0x14003df45  jz      short loc_14003DF83
0x14003df47  test    byte ptr [rcx+1Ch], 8
0x14003df4b  jz      short loc_14003DF83
0x14003df4d  cmp     byte ptr [rcx+19h], 2
0x14003df51  jb      short loc_14003DF83
0x14003df53  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003df58  lea     rcx, aFailedToRemove_24; "Failed to remove DATA_CHANNEL_REQUEST e"...
0x14003df5f  mov     dword ptr [rsp+58h+var_30], edi
0x14003df63  mov     [rsp+58h+var_38], rcx
0x14003df68  mov     edx, 37h ; '7'
0x14003df6d  mov     rcx, cs:WPP_GLOBAL_Control
0x14003df74  mov     r9d, eax
0x14003df77  mov     r8, r15
0x14003df7a  mov     rcx, [rcx+10h]
0x14003df7e  call    WPP_SF_DsD
0x14003df83  mov     rcx, [rbx+2A8h]
0x14003df8a  lea     r8, [rbx+380h]
0x14003df91  mov     edx, 0ABh
0x14003df96  mov     rax, [rcx]
0x14003df99  mov     rax, [rax+60h]
0x14003df9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003dfa2  mov     edi, eax
0x14003dfa4  test    eax, eax
0x14003dfa6  jns     short loc_14003DFF0
0x14003dfa8  mov     rcx, cs:WPP_GLOBAL_Control
0x14003dfaf  cmp     rcx, r14
0x14003dfb2  jz      short loc_14003DFF0
0x14003dfb4  test    byte ptr [rcx+1Ch], 8
0x14003dfb8  jz      short loc_14003DFF0
0x14003dfba  cmp     byte ptr [rcx+19h], 2
0x14003dfbe  jb      short loc_14003DFF0
0x14003dfc0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003dfc5  lea     rcx, aFailedToRemove_8; "Failed to remove DATA_CHANNEL_RESPONSE "...
0x14003dfcc  mov     dword ptr [rsp+58h+var_30], edi
0x14003dfd0  mov     [rsp+58h+var_38], rcx
0x14003dfd5  mov     edx, 38h ; '8'
0x14003dfda  mov     rcx, cs:WPP_GLOBAL_Control
0x14003dfe1  mov     r9d, eax
0x14003dfe4  mov     r8, r15
0x14003dfe7  mov     rcx, [rcx+10h]
0x14003dfeb  call    WPP_SF_DsD
0x14003dff0  mov     rcx, [rbx+2A8h]
0x14003dff7  lea     r8, [rbx+388h]
0x14003dffe  mov     edx, 0ADh
0x14003e003  mov     rax, [rcx]
0x14003e006  mov     rax, [rax+60h]
0x14003e00a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e00f  mov     edi, eax
0x14003e011  test    eax, eax
0x14003e013  jns     short loc_14003E05D
0x14003e015  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e01c  cmp     rcx, r14
0x14003e01f  jz      short loc_14003E05D
0x14003e021  test    byte ptr [rcx+1Ch], 8
0x14003e025  jz      short loc_14003E05D
0x14003e027  cmp     byte ptr [rcx+19h], 2
0x14003e02b  jb      short loc_14003E05D
0x14003e02d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003e032  lea     rcx, aFailedToRemove_17; "Failed to remove DATA_CHANNEL_ACCEPTED "...
0x14003e039  mov     dword ptr [rsp+58h+var_30], edi
0x14003e03d  mov     [rsp+58h+var_38], rcx
0x14003e042  mov     edx, 39h ; '9'
0x14003e047  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e04e  mov     r9d, eax
0x14003e051  mov     r8, r15
0x14003e054  mov     rcx, [rcx+10h]
0x14003e058  call    WPP_SF_DsD
0x14003e05d  mov     rcx, [rbx+2A8h]
0x14003e064  lea     r8, [rbx+370h]
0x14003e06b  mov     edx, 9Bh
0x14003e070  mov     rax, [rcx]
0x14003e073  mov     rax, [rax+60h]
0x14003e077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e07c  mov     edi, eax
0x14003e07e  test    eax, eax
0x14003e080  jns     short loc_14003E0CA
0x14003e082  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e089  cmp     rcx, r14
0x14003e08c  jz      short loc_14003E0CA
0x14003e08e  test    byte ptr [rcx+1Ch], 8
0x14003e092  jz      short loc_14003E0CA
0x14003e094  cmp     byte ptr [rcx+19h], 2
0x14003e098  jb      short loc_14003E0CA
0x14003e09a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003e09f  lea     rcx, aFailedToRemove_16; "Failed to remove FORMAT_LIST event sink"...
0x14003e0a6  mov     dword ptr [rsp+58h+var_30], edi
0x14003e0aa  mov     [rsp+58h+var_38], rcx
0x14003e0af  mov     edx, 3Ah ; ':'
0x14003e0b4  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e0bb  mov     r9d, eax
0x14003e0be  mov     r8, r15
0x14003e0c1  mov     rcx, [rcx+10h]
0x14003e0c5  call    WPP_SF_DsD
0x14003e0ca  mov     rcx, rbx; this
0x14003e0cd  call    ?RemoveNotificationSinks@CClipBase@@MEAAJXZ; CClipBase::RemoveNotificationSinks(void)
0x14003e0d2  mov     ebx, eax
0x14003e0d4  test    eax, eax
0x14003e0d6  jns     short loc_14003E120
0x14003e0d8  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e0df  cmp     rcx, r14
0x14003e0e2  jz      short loc_14003E120
0x14003e0e4  test    byte ptr [rcx+1Ch], 8
0x14003e0e8  jz      short loc_14003E120
0x14003e0ea  cmp     byte ptr [rcx+19h], 2
0x14003e0ee  jb      short loc_14003E120
0x14003e0f0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003e0f5  lea     rcx, aCclipbaseRemov; "CClipBase::RemoveNotificationSinks fail"...
0x14003e0fc  mov     dword ptr [rsp+58h+var_30], ebx
0x14003e100  mov     [rsp+58h+var_38], rcx
0x14003e105  mov     edx, 3Bh ; ';'
0x14003e10a  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e111  mov     r9d, eax
0x14003e114  mov     r8, r15
0x14003e117  mov     rcx, [rcx+10h]
0x14003e11b  call    WPP_SF_DsD
0x14003e120  xor     eax, eax
0x14003e122  add     rsp, 38h
0x14003e126  pop     r15
0x14003e128  pop     r14
0x14003e12a  pop     rdi
0x14003e12b  pop     rbx
0x14003e12c  retn
```
