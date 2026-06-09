# CHNetConn::GetGuid(_GUID * *)

- ea: `0x18001bca0`
- end: `0x18001be0a`
- name: `?GetGuid@CHNetConn@@UEAAJPEAPEAU_GUID@@@Z`
- size: `362`
- prototype: `__int64 __fastcall(CHNetConn *__hidden this, struct _GUID **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000a45c`
- `0x18000a484`
- `0x18001bca0`
- `0x18001be10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001bd31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001bd31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bdb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bdb0`

## pseudocode

```c
__int64 __fastcall CHNetConn::GetGuid(CHNetConn *this, struct _GUID **a2)
{
  PVOID *v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rdx
  struct _GUID *v7; // rax
  int GuidInternal; // eax
  struct _GUID *v9; // rcx
  struct _GUID *v11; // [rsp+58h] [rbp+10h] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    v7 = (struct _GUID *)CoTaskMemAlloc(0x10u);
    *a2 = v7;
    if ( v7 )
    {
      v11 = 0;
      GuidInternal = CHNetConn::GetGuidInternal(this, &v11);
      v5 = GuidInternal;
      if ( GuidInternal >= 0
        || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        v9 = *a2;
        if ( GuidInternal >= 0 )
        {
          *v9 = *v11;
          goto LABEL_22;
        }
      }
      else
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          54,
          WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
          (unsigned int)GuidInternal);
        v9 = *a2;
      }
      CoTaskMemFree(v9);
      *a2 = 0;
LABEL_22:
      v4 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_23;
    }
    v5 = -2147024882;
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v5;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_23;
    v6 = 53;
LABEL_10:
    WPP_SF_d(v4[2], v6, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, v5);
    goto LABEL_22;
  }
  v5 = -2147467261;
  if ( v4 == &WPP_GLOBAL_Control )
    return v5;
  if ( (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 2u )
  {
    v6 = 52;
    goto LABEL_10;
  }
LABEL_23:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 6u )
    WPP_SF_d(v4[2], 55, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x18001bca0  push    rbx
0x18001bca2  push    rbp
0x18001bca3  push    rdi
0x18001bca4  push    r14
0x18001bca6  sub     rsp, 28h
0x18001bcaa  mov     rdi, rdx
0x18001bcad  mov     rbx, rcx
0x18001bcb0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bcb7  lea     rbp, WPP_GLOBAL_Control
0x18001bcbe  lea     r14, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001bcc5  cmp     rcx, rbp
0x18001bcc8  jz      short loc_18001BCEE
0x18001bcca  test    byte ptr [rcx+1Ch], 8
0x18001bcce  jz      short loc_18001BCEE
0x18001bcd0  cmp     byte ptr [rcx+19h], 6
0x18001bcd4  jb      short loc_18001BCEE
0x18001bcd6  mov     rcx, [rcx+10h]
0x18001bcda  mov     edx, 33h ; '3'
0x18001bcdf  mov     r8, r14
0x18001bce2  call    WPP_SF_
0x18001bce7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bcee  test    rdi, rdi
0x18001bcf1  jnz     short loc_18001BD2C
0x18001bcf3  mov     ebx, 80004003h
0x18001bcf8  cmp     rcx, rbp
0x18001bcfb  jz      loc_18001BDE9
0x18001bd01  test    byte ptr [rcx+1Ch], 8
0x18001bd05  jz      loc_18001BDC4
0x18001bd0b  cmp     byte ptr [rcx+19h], 2
0x18001bd0f  jb      loc_18001BDC4
0x18001bd15  lea     edx, [rdi+34h]
0x18001bd18  mov     rcx, [rcx+10h]
0x18001bd1c  mov     r9d, ebx
0x18001bd1f  mov     r8, r14
0x18001bd22  call    WPP_SF_d
0x18001bd27  jmp     loc_18001BDBD
0x18001bd2c  mov     ecx, 10h; cb
0x18001bd31  call    cs:__imp_CoTaskMemAlloc
0x18001bd37  mov     [rdi], rax
0x18001bd3a  test    rax, rax
0x18001bd3d  jnz     short loc_18001BD65
0x18001bd3f  mov     ebx, 8007000Eh
0x18001bd44  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd4b  cmp     rcx, rbp
0x18001bd4e  jz      loc_18001BDE9
0x18001bd54  test    byte ptr [rcx+1Ch], 8
0x18001bd58  jz      short loc_18001BDC4
0x18001bd5a  cmp     byte ptr [rcx+19h], 2
0x18001bd5e  jb      short loc_18001BDC4
0x18001bd60  lea     edx, [rax+35h]
0x18001bd63  jmp     short loc_18001BD18
0x18001bd65  lea     rdx, [rsp+48h+arg_8]; struct _GUID **
0x18001bd6a  mov     [rsp+48h+arg_8], 0
0x18001bd73  mov     rcx, rbx; this
0x18001bd76  call    ?GetGuidInternal@CHNetConn@@IEAAJPEAPEAU_GUID@@@Z; CHNetConn::GetGuidInternal(_GUID * *)
0x18001bd7b  mov     ebx, eax
0x18001bd7d  test    eax, eax
0x18001bd7f  jns     short loc_18001BDF5
0x18001bd81  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd88  cmp     rcx, rbp
0x18001bd8b  jz      short loc_18001BDF5
0x18001bd8d  test    byte ptr [rcx+1Ch], 8
0x18001bd91  jz      short loc_18001BDF5
0x18001bd93  cmp     byte ptr [rcx+19h], 2
0x18001bd97  jb      short loc_18001BDF5
0x18001bd99  mov     rcx, [rcx+10h]
0x18001bd9d  mov     edx, 36h ; '6'
0x18001bda2  mov     r9d, eax
0x18001bda5  mov     r8, r14
0x18001bda8  call    WPP_SF_d
0x18001bdad  mov     rcx, [rdi]; pv
0x18001bdb0  call    cs:__imp_CoTaskMemFree
0x18001bdb6  mov     qword ptr [rdi], 0
0x18001bdbd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bdc4  cmp     rcx, rbp
0x18001bdc7  jz      short loc_18001BDE9
0x18001bdc9  test    byte ptr [rcx+1Ch], 8
0x18001bdcd  jz      short loc_18001BDE9
0x18001bdcf  cmp     byte ptr [rcx+19h], 6
0x18001bdd3  jb      short loc_18001BDE9
0x18001bdd5  mov     rcx, [rcx+10h]
0x18001bdd9  mov     edx, 37h ; '7'
0x18001bdde  mov     r9d, ebx
0x18001bde1  mov     r8, r14
0x18001bde4  call    WPP_SF_d
0x18001bde9  mov     eax, ebx
0x18001bdeb  add     rsp, 28h
0x18001bdef  pop     r14
0x18001bdf1  pop     rdi
0x18001bdf2  pop     rbp
0x18001bdf3  pop     rbx
0x18001bdf4  retn
0x18001bdf5  mov     rcx, [rdi]
0x18001bdf8  test    eax, eax
0x18001bdfa  js      short loc_18001BDB0
0x18001bdfc  mov     rax, [rsp+48h+arg_8]
0x18001be01  movups  xmm0, xmmword ptr [rax]
0x18001be04  movdqu  xmmword ptr [rcx], xmm0
0x18001be08  jmp     short loc_18001BDBD
```
