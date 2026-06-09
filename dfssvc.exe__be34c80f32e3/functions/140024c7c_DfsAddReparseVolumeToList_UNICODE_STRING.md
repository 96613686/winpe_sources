# DfsAddReparseVolumeToList(_UNICODE_STRING *)

- ea: `0x140024c7c`
- end: `0x140024f43`
- name: `?DfsAddReparseVolumeToList@@YAKPEAU_UNICODE_STRING@@@Z`
- size: `711`
- prototype: `unsigned int __fastcall(struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x140036e08`

## callees

- `0x1400011c4`
- `0x140005a94`
- `0x1400096ac`
- `0x14000fca8`
- `0x140024c7c`
- `0x1400257e4`
- `0x140025994`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x140024df0`
- `ntdll!RtlCompareUnicodeString` at `0x140024df0`
- `ntdll!RtlInitUnicodeString` at `0x140024ca5`
- `ntdll!RtlInitUnicodeString` at `0x140024ca5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140024dc5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140024dc5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140024ec3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140024ec3`

## pseudocode

```c
__int64 __fastcall DfsAddReparseVolumeToList(struct _UNICODE_STRING *a1)
{
  unsigned int *v2; // rcx
  PWSTR Buffer; // rax
  unsigned int VolumePathName; // eax
  unsigned int v5; // edi
  __int64 *i; // rbx
  unsigned int v7; // eax
  UNICODE_STRING String2; // [rsp+20h] [rbp-18h] BYREF

  String2 = 0;
  RtlInitUnicodeString(&String2, 0);
  v2 = pWppControl;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x20) != 0
    && *((_BYTE *)pWppControl + 25) >= 2u )
  {
    WPP_SF_Z(*((_QWORD *)pWppControl + 2), 26, WPP_06cdb52cbe4531ba727f9e22c79a690d_Traceguids, a1);
    v2 = pWppControl;
  }
  if ( a1 && a1->Length && (Buffer = a1->Buffer) != 0 && *Buffer )
  {
    VolumePathName = DfsGetVolumePathName(a1, &String2);
    v5 = VolumePathName;
    if ( !VolumePathName )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && pWppControl
        && (pWppControl[7] & 0x20) != 0
        && *((_BYTE *)pWppControl + 25) >= 2u )
      {
        WPP_SF_Z(*((_QWORD *)pWppControl + 2), 28, WPP_06cdb52cbe4531ba727f9e22c79a690d_Traceguids, &String2);
      }
      EnterCriticalSection(&CriticalSection);
      for ( i = (__int64 *)qword_140071618; i != &qword_140071618; i = (__int64 *)*i )
      {
        if ( !RtlCompareUnicodeString((PCUNICODE_STRING)i - 1, &String2, 1u) )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && pWppControl
            && (pWppControl[7] & 0x20) != 0
            && *((_BYTE *)pWppControl + 25) >= 2u )
          {
            WPP_SF_(*((_QWORD *)pWppControl + 2), 29, WPP_06cdb52cbe4531ba727f9e22c79a690d_Traceguids);
          }
          goto LABEL_41;
        }
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && pWppControl
        && (pWppControl[7] & 0x20) != 0
        && *((_BYTE *)pWppControl + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)pWppControl + 2), 30, WPP_06cdb52cbe4531ba727f9e22c79a690d_Traceguids);
      }
      v7 = DfsInsertInReparseVolList(String2.Buffer);
      v5 = v7;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && pWppControl
        && (pWppControl[7] & 0x20) != 0
        && *((_BYTE *)pWppControl + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)pWppControl + 2), 31, WPP_06cdb52cbe4531ba727f9e22c79a690d_Traceguids, v7);
      }
LABEL_41:
      LeaveCriticalSection(&CriticalSection);
      goto LABEL_16;
    }
    v2 = pWppControl;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && pWppControl
      && (pWppControl[7] & 0x20) != 0
      && *((_BYTE *)pWppControl + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)pWppControl + 2), 27, WPP_06cdb52cbe4531ba727f9e22c79a690d_Traceguids, VolumePathName);
LABEL_16:
      v2 = pWppControl;
    }
  }
  else
  {
    v5 = 1168;
  }
  if ( String2.Buffer )
  {
    operator delete(String2.Buffer);
    v2 = pWppControl;
    String2.Buffer = 0;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && v2 && (v2[7] & 0x20) != 0 && *((_BYTE *)v2 + 25) >= 2u )
    WPP_SF_D(*((_QWORD *)v2 + 2), 32, WPP_06cdb52cbe4531ba727f9e22c79a690d_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x140024c7c  mov     rax, rsp
0x140024c7f  mov     [rax+8], rbx
0x140024c83  mov     [rax+10h], rsi
0x140024c87  mov     [rax+18h], rdi
0x140024c8b  mov     [rax+20h], r12
0x140024c8f  push    r15
0x140024c91  sub     rsp, 30h
0x140024c95  mov     rbx, rcx
0x140024c98  xorps   xmm0, xmm0
0x140024c9b  lea     rcx, [rax-18h]; DestinationString
0x140024c9f  xor     edx, edx; SourceString
0x140024ca1  movups  xmmword ptr [rax-18h], xmm0
0x140024ca5  call    cs:__imp_RtlInitUnicodeString
0x140024cac  nop     dword ptr [rax+rax+00h]
0x140024cb1  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140024cb8  lea     r15, WPP_GLOBAL_Control
0x140024cbf  xor     esi, esi
0x140024cc1  lea     r12, WPP_06cdb52cbe4531ba727f9e22c79a690d_Traceguids
0x140024cc8  cmp     cs:WPP_GLOBAL_Control, r15
0x140024ccf  jz      short loc_140024CFB
0x140024cd1  test    rcx, rcx
0x140024cd4  jz      short loc_140024CFB
0x140024cd6  test    byte ptr [rcx+1Ch], 20h
0x140024cda  jz      short loc_140024CFB
0x140024cdc  cmp     byte ptr [rcx+19h], 2
0x140024ce0  jb      short loc_140024CFB
0x140024ce2  mov     rcx, [rcx+10h]
0x140024ce6  lea     edx, [rsi+1Ah]
0x140024ce9  mov     r9, rbx
0x140024cec  mov     r8, r12
0x140024cef  call    WPP_SF_Z
0x140024cf4  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140024cfb  test    rbx, rbx
0x140024cfe  jz      loc_140024ED4
0x140024d04  cmp     [rbx], si
0x140024d07  jz      loc_140024ED4
0x140024d0d  mov     rax, [rbx+8]
0x140024d11  test    rax, rax
0x140024d14  jz      loc_140024ED4
0x140024d1a  cmp     [rax], si
0x140024d1d  jz      loc_140024ED4
0x140024d23  lea     rdx, [rsp+38h+String2]; struct _UNICODE_STRING *
0x140024d28  mov     rcx, rbx; struct _UNICODE_STRING *
0x140024d2b  call    ?DfsGetVolumePathName@@YAKPEAU_UNICODE_STRING@@0@Z; DfsGetVolumePathName(_UNICODE_STRING *,_UNICODE_STRING *)
0x140024d30  mov     edi, eax
0x140024d32  test    eax, eax
0x140024d34  jz      short loc_140024D87
0x140024d36  cmp     cs:WPP_GLOBAL_Control, r15
0x140024d3d  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140024d44  jz      loc_140024ED9
0x140024d4a  test    rcx, rcx
0x140024d4d  jz      loc_140024ED9
0x140024d53  test    byte ptr [rcx+1Ch], 20h
0x140024d57  jz      loc_140024ED9
0x140024d5d  cmp     byte ptr [rcx+19h], 2
0x140024d61  jb      loc_140024ED9
0x140024d67  mov     rcx, [rcx+10h]
0x140024d6b  mov     edx, 1Bh
0x140024d70  mov     r9d, eax
0x140024d73  mov     r8, r12
0x140024d76  call    WPP_SF_D
0x140024d7b  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140024d82  jmp     loc_140024ED9
0x140024d87  cmp     cs:WPP_GLOBAL_Control, r15
0x140024d8e  jz      short loc_140024DBE
0x140024d90  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140024d97  test    rcx, rcx
0x140024d9a  jz      short loc_140024DBE
0x140024d9c  test    byte ptr [rcx+1Ch], 20h
0x140024da0  jz      short loc_140024DBE
0x140024da2  cmp     byte ptr [rcx+19h], 2
0x140024da6  jb      short loc_140024DBE
0x140024da8  mov     rcx, [rcx+10h]
0x140024dac  lea     r9, [rsp+38h+String2]
0x140024db1  mov     edx, 1Ch
0x140024db6  mov     r8, r12
0x140024db9  call    WPP_SF_Z
0x140024dbe  lea     rcx, CriticalSection; lpCriticalSection
0x140024dc5  call    cs:__imp_EnterCriticalSection
0x140024dcc  nop     dword ptr [rax+rax+00h]
0x140024dd1  mov     rbx, cs:qword_140071618
0x140024dd8  lea     rax, qword_140071618
0x140024ddf  cmp     rbx, rax
0x140024de2  jz      short loc_140024E49
0x140024de4  lea     rcx, [rbx-10h]; String1
0x140024de8  mov     r8b, 1; CaseInsensitive
0x140024deb  lea     rdx, [rsp+38h+String2]; String2
0x140024df0  call    cs:__imp_RtlCompareUnicodeString
0x140024df7  nop     dword ptr [rax+rax+00h]
0x140024dfc  test    eax, eax
0x140024dfe  jz      short loc_140024E05
0x140024e00  mov     rbx, [rbx]
0x140024e03  jmp     short loc_140024DD8
0x140024e05  cmp     cs:WPP_GLOBAL_Control, r15
0x140024e0c  jz      loc_140024EBC
0x140024e12  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140024e19  test    rcx, rcx
0x140024e1c  jz      loc_140024EBC
0x140024e22  test    byte ptr [rcx+1Ch], 20h
0x140024e26  jz      loc_140024EBC
0x140024e2c  cmp     byte ptr [rcx+19h], 2
0x140024e30  jb      loc_140024EBC
0x140024e36  mov     rcx, [rcx+10h]
0x140024e3a  mov     edx, 1Dh
0x140024e3f  mov     r8, r12
0x140024e42  call    WPP_SF_
0x140024e47  jmp     short loc_140024EBC
0x140024e49  cmp     cs:WPP_GLOBAL_Control, r15
0x140024e50  jz      short loc_140024E7B
0x140024e52  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140024e59  test    rcx, rcx
0x140024e5c  jz      short loc_140024E7B
0x140024e5e  test    byte ptr [rcx+1Ch], 20h
0x140024e62  jz      short loc_140024E7B
0x140024e64  cmp     byte ptr [rcx+19h], 2
0x140024e68  jb      short loc_140024E7B
0x140024e6a  mov     rcx, [rcx+10h]
0x140024e6e  mov     edx, 1Eh
0x140024e73  mov     r8, r12
0x140024e76  call    WPP_SF_
0x140024e7b  mov     rcx, [rsp+38h+String2.Buffer]; unsigned __int16 *
0x140024e80  call    ?DfsInsertInReparseVolList@@YAKPEAG@Z; DfsInsertInReparseVolList(ushort *)
0x140024e85  mov     edi, eax
0x140024e87  cmp     cs:WPP_GLOBAL_Control, r15
0x140024e8e  jz      short loc_140024EBC
0x140024e90  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140024e97  test    rcx, rcx
0x140024e9a  jz      short loc_140024EBC
0x140024e9c  test    byte ptr [rcx+1Ch], 20h
0x140024ea0  jz      short loc_140024EBC
0x140024ea2  cmp     byte ptr [rcx+19h], 2
0x140024ea6  jb      short loc_140024EBC
0x140024ea8  mov     rcx, [rcx+10h]
0x140024eac  mov     edx, 1Fh
0x140024eb1  mov     r9d, eax
0x140024eb4  mov     r8, r12
0x140024eb7  call    WPP_SF_D
0x140024ebc  lea     rcx, CriticalSection; lpCriticalSection
0x140024ec3  call    cs:__imp_LeaveCriticalSection
0x140024eca  nop     dword ptr [rax+rax+00h]
0x140024ecf  jmp     loc_140024D7B
0x140024ed4  mov     edi, 490h
0x140024ed9  mov     rax, [rsp+38h+String2.Buffer]
0x140024ede  test    rax, rax
0x140024ee1  jz      short loc_140024EF7
0x140024ee3  mov     rcx, rax; Block
0x140024ee6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140024eeb  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140024ef2  mov     [rsp+38h+String2.Buffer], rsi
0x140024ef7  cmp     cs:WPP_GLOBAL_Control, r15
0x140024efe  jz      short loc_140024F25
0x140024f00  test    rcx, rcx
0x140024f03  jz      short loc_140024F25
0x140024f05  test    byte ptr [rcx+1Ch], 20h
0x140024f09  jz      short loc_140024F25
0x140024f0b  cmp     byte ptr [rcx+19h], 2
0x140024f0f  jb      short loc_140024F25
0x140024f11  mov     rcx, [rcx+10h]
0x140024f15  mov     edx, 20h ; ' '
0x140024f1a  mov     r9d, edi
0x140024f1d  mov     r8, r12
0x140024f20  call    WPP_SF_D
0x140024f25  mov     rbx, [rsp+38h+arg_0]
0x140024f2a  mov     eax, edi
0x140024f2c  mov     rdi, [rsp+38h+arg_10]
0x140024f31  mov     rsi, [rsp+38h+arg_8]
0x140024f36  mov     r12, [rsp+38h+arg_18]
0x140024f3b  add     rsp, 30h
0x140024f3f  pop     r15
0x140024f41  retn
```
