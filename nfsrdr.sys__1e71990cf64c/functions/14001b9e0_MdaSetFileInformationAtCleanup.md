# MdaSetFileInformationAtCleanup

- ea: `0x14001b9e0`
- end: `0x14001bbb4`
- name: `MdaSetFileInformationAtCleanup`
- size: `468`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x1400159cc`
- `0x1400159fc`
- `0x14001b9e0`
- `0x14001d6b0`

## pseudocode

```c
__int64 __fastcall MdaSetFileInformationAtCleanup(__int64 a1)
{
  int v1; // eax
  int v2; // ebx
  __int64 v3; // rsi
  __int64 v4; // rbp
  unsigned int v5; // edi
  __int64 v6; // r14
  unsigned int v7; // ebx

  v1 = *(_DWORD *)(a1 + 120);
  v2 = a1;
  if ( (v1 & 0x1000) != 0 )
  {
    if ( (v1 & 2) == 0 )
    {
      *(_BYTE *)(a1 + 35) = 1;
      return 3225485315LL;
    }
    *(_DWORD *)(a1 + 120) = v1 & 0xFFFFEFFF;
  }
  v3 = *(_QWORD *)(a1 + 56);
  v4 = *(_QWORD *)(a1 + 64);
  v5 = *(_DWORD *)(a1 + 448);
  v6 = *(_QWORD *)(a1 + 456);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids, v5);
  }
  if ( v5 == 4 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids);
    v7 = 0;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return v7;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids, 0);
    goto LABEL_30;
  }
  if ( v5 == 20 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids);
    v7 = MdaSetSizeInformation(v2, v3, v4, 20, v6);
    if ( (v7 & 0x80000000) == 0 )
      goto LABEL_30;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids, v5);
    v7 = -1073741811;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 48, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids, v7);
LABEL_30:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 49, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids);
  }
  return v7;
}

```

## disassembly

```asm
0x14001b9e0  push    rbx
0x14001b9e2  push    rbp
0x14001b9e3  push    rsi
0x14001b9e4  push    rdi
0x14001b9e5  push    r12
0x14001b9e7  push    r14
0x14001b9e9  push    r15
0x14001b9eb  sub     rsp, 30h
0x14001b9ef  mov     eax, [rcx+78h]
0x14001b9f2  mov     rbx, rcx
0x14001b9f5  bt      eax, 0Ch
0x14001b9f9  jnb     short loc_14001BA0A
0x14001b9fb  test    al, 2
0x14001b9fd  jz      loc_14001BAB4
0x14001ba03  btr     eax, 0Ch
0x14001ba07  mov     [rcx+78h], eax
0x14001ba0a  mov     rsi, [rcx+38h]
0x14001ba0e  lea     r15, WPP_GLOBAL_Control
0x14001ba15  mov     rbp, [rcx+40h]
0x14001ba19  lea     r12, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids
0x14001ba20  mov     edi, [rcx+1C0h]
0x14001ba26  mov     r14, [rcx+1C8h]
0x14001ba2d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ba34  cmp     rcx, r15
0x14001ba37  jz      short loc_14001BA78
0x14001ba39  mov     eax, [rcx+2Ch]
0x14001ba3c  test    al, 8
0x14001ba3e  jz      short loc_14001BA51
0x14001ba40  mov     rcx, [rcx+18h]
0x14001ba44  mov     edx, 2Ah ; '*'
0x14001ba49  mov     r8, r12
0x14001ba4c  call    WPP_SF_
0x14001ba51  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ba58  cmp     rcx, r15
0x14001ba5b  jz      short loc_14001BA78
0x14001ba5d  mov     eax, [rcx+2Ch]
0x14001ba60  test    al, 4
0x14001ba62  jz      short loc_14001BA78
0x14001ba64  mov     rcx, [rcx+18h]
0x14001ba68  mov     edx, 2Bh ; '+'
0x14001ba6d  mov     r9d, edi
0x14001ba70  mov     r8, r12
0x14001ba73  call    WPP_SF_d
0x14001ba78  cmp     edi, 4
0x14001ba7b  jz      loc_14001BB32
0x14001ba81  cmp     edi, 14h
0x14001ba84  jz      short loc_14001BAC2
0x14001ba86  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ba8d  cmp     rcx, r15
0x14001ba90  jz      short loc_14001BAAD
0x14001ba92  mov     eax, [rcx+2Ch]
0x14001ba95  test    al, 4
0x14001ba97  jz      short loc_14001BAAD
0x14001ba99  mov     rcx, [rcx+18h]
0x14001ba9d  mov     edx, 2Fh ; '/'
0x14001baa2  mov     r9d, edi
0x14001baa5  mov     r8, r12
0x14001baa8  call    WPP_SF_d
0x14001baad  mov     ebx, 0C000000Dh
0x14001bab2  jmp     short loc_14001BB05
0x14001bab4  mov     byte ptr [rcx+23h], 1
0x14001bab8  mov     eax, 0C0410003h
0x14001babd  jmp     loc_14001BBA4
0x14001bac2  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bac9  cmp     rcx, r15
0x14001bacc  jz      short loc_14001BAE6
0x14001bace  mov     eax, [rcx+2Ch]
0x14001bad1  test    al, 4
0x14001bad3  jz      short loc_14001BAE6
0x14001bad5  mov     rcx, [rcx+18h]
0x14001bad9  mov     edx, 2Eh ; '.'
0x14001bade  mov     r8, r12
0x14001bae1  call    WPP_SF_
0x14001bae6  mov     r9d, 14h
0x14001baec  mov     [rsp+68h+var_48], r14
0x14001baf1  mov     r8, rbp
0x14001baf4  mov     rdx, rsi
0x14001baf7  mov     rcx, rbx
0x14001bafa  call    MdaSetSizeInformation
0x14001baff  mov     ebx, eax
0x14001bb01  test    eax, eax
0x14001bb03  jns     short loc_14001BB7D
0x14001bb05  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bb0c  cmp     rcx, r15
0x14001bb0f  jz      loc_14001BBA2
0x14001bb15  mov     eax, [rcx+2Ch]
0x14001bb18  test    al, 1
0x14001bb1a  jz      short loc_14001BB7D
0x14001bb1c  mov     rcx, [rcx+18h]
0x14001bb20  mov     edx, 30h ; '0'
0x14001bb25  mov     r9d, ebx
0x14001bb28  mov     r8, r12
0x14001bb2b  call    WPP_SF_d
0x14001bb30  jmp     short loc_14001BB7D
0x14001bb32  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bb39  cmp     rcx, r15
0x14001bb3c  jz      short loc_14001BB56
0x14001bb3e  mov     eax, [rcx+2Ch]
0x14001bb41  test    al, 4
0x14001bb43  jz      short loc_14001BB56
0x14001bb45  mov     rcx, [rcx+18h]
0x14001bb49  mov     edx, 2Ch ; ','
0x14001bb4e  mov     r8, r12
0x14001bb51  call    WPP_SF_
0x14001bb56  xor     ebx, ebx
0x14001bb58  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bb5f  cmp     rcx, r15
0x14001bb62  jz      short loc_14001BBA2
0x14001bb64  mov     eax, [rcx+2Ch]
0x14001bb67  test    al, 4
0x14001bb69  jz      short loc_14001BB7D
0x14001bb6b  mov     rcx, [rcx+18h]
0x14001bb6f  lea     edx, [rbx+2Dh]
0x14001bb72  xor     r9d, r9d
0x14001bb75  mov     r8, r12
0x14001bb78  call    WPP_SF_d
0x14001bb7d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bb84  cmp     rcx, r15
0x14001bb87  jz      short loc_14001BBA2
0x14001bb89  mov     edx, [rcx+2Ch]
0x14001bb8c  test    dl, 8
0x14001bb8f  jz      short loc_14001BBA2
0x14001bb91  mov     rcx, [rcx+18h]
0x14001bb95  mov     edx, 31h ; '1'
0x14001bb9a  mov     r8, r12
0x14001bb9d  call    WPP_SF_
0x14001bba2  mov     eax, ebx
0x14001bba4  add     rsp, 30h
0x14001bba8  pop     r15
0x14001bbaa  pop     r14
0x14001bbac  pop     r12
0x14001bbae  pop     rdi
0x14001bbaf  pop     rsi
0x14001bbb0  pop     rbp
0x14001bbb1  pop     rbx
0x14001bbb2  retn
```
