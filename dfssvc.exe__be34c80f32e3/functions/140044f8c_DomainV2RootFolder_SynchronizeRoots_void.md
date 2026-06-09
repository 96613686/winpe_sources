# DomainV2RootFolder::SynchronizeRoots(void)

- ea: `0x140044f8c`
- end: `0x140045143`
- name: `?SynchronizeRoots@DomainV2RootFolder@@QEAAXXZ`
- size: `439`
- prototype: `void __fastcall(DomainV2RootFolder *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140044cd0`

## callees

- `0x1400096ac`
- `0x14000abc4`
- `0x14000b890`
- `0x1400170d4`
- `0x14003aed4`
- `0x140044f8c`
- `0x14004a454`
- `0x140058b04`
- `0x140058db8`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x14004507c`
- `ntdll!RtlCompareUnicodeString` at `0x14004507c`
- `ntdll!RtlInitUnicodeStringEx` at `0x14004504f`
- `ntdll!RtlInitUnicodeStringEx` at `0x14004504f`

## pseudocode

```c
void __fastcall DomainV2RootFolder::SynchronizeRoots(DomainV2RootFolder *this)
{
  int v1; // r14d
  int v2; // r15d
  bool v3; // zf
  char *v4; // r13
  DfsGeneric *v5; // rdi
  const WCHAR *LocalMachineName; // rax
  unsigned int i; // esi
  __int64 v8; // rbx
  unsigned int v9; // ebx
  int v10; // edx
  int v11; // [rsp+28h] [rbp-28h]
  struct _UNICODE_STRING v12; // [rsp+30h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int8 v14; // [rsp+80h] [rbp+30h] BYREF
  DfsGeneric *v15; // [rsp+88h] [rbp+38h] BYREF

  v15 = 0;
  v1 = 0;
  v14 = 0;
  LOBYTE(v2) = 0;
  v3 = *((_BYTE *)this + 448) == 1;
  v12 = 0;
  DestinationString = 0;
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && pWppControl
      && (pWppControl[7] & 0x20) != 0
      && *((_BYTE *)pWppControl + 25) >= 3u )
    {
      WPP_SF_(*((_QWORD *)pWppControl + 2), 24, WPP_025da0f6f4563439d7f6acd58192d4f6_Traceguids);
    }
  }
  else
  {
    v4 = (char *)this + 296;
    if ( !DfsFolder::GetReferralData(this, &v15, &v14, 1u) )
    {
      v5 = v15;
      v2 = *((_DWORD *)v15 + 10);
      LocalMachineName = (const WCHAR *)DfsGetLocalMachineName(3);
      RtlInitUnicodeStringEx(&DestinationString, LocalMachineName);
      for ( i = 0; i < *((_DWORD *)v5 + 10); ++i )
      {
        v8 = *(_QWORD *)(56LL * i + *((_QWORD *)v5 + 6) + 16);
        if ( RtlCompareUnicodeString((PCUNICODE_STRING)(v8 + 24), &DestinationString, 1u) )
        {
          if ( !(unsigned int)DfsCreateUnicodePathString(&v12, 2, *(_QWORD *)(v8 + 32), *((_QWORD *)v4 + 1)) )
          {
            v9 = AddRootToSyncrhonize(&v12);
            DfsFreeUnicodeString(&v12);
            v10 = v1 + 1;
            if ( v9 )
              v10 = v1;
            v1 = v10;
          }
          if ( HIBYTE(word_140071515) == 1 )
            break;
        }
      }
      DfsGeneric::ReleaseReference(v5);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && pWppControl
      && (pWppControl[7] & 0x20) != 0
      && *((_BYTE *)pWppControl + 25) >= 3u )
    {
      v11 = v1;
      WPP_SF_ZDd(
        *((_QWORD *)pWppControl + 2),
        25,
        (unsigned int)WPP_025da0f6f4563439d7f6acd58192d4f6_Traceguids,
        (_DWORD)v4,
        v2,
        v11,
        *(_QWORD *)&v12.Length,
        v12.Buffer,
        *(_QWORD *)&DestinationString.Length,
        DestinationString.Buffer);
    }
  }
}

```

## disassembly

```asm
0x140044f8c  mov     [rsp-28h+arg_10], rbx
0x140044f91  mov     [rsp-28h+arg_18], rsi
0x140044f96  push    rbp
0x140044f97  push    rdi
0x140044f98  push    r13
0x140044f9a  push    r14
0x140044f9c  push    r15
0x140044f9e  mov     rbp, rsp
0x140044fa1  sub     rsp, 50h
0x140044fa5  and     [rbp+arg_8], 0
0x140044faa  xor     r14d, r14d
0x140044fad  xorps   xmm0, xmm0
0x140044fb0  mov     [rbp+arg_0], r14b
0x140044fb4  xor     r15d, r15d
0x140044fb7  cmp     byte ptr [rcx+1C0h], 1
0x140044fbe  movups  xmmword ptr [rbp+var_20.Length], xmm0
0x140044fc2  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140044fc6  jnz     short loc_140045019
0x140044fc8  lea     rax, WPP_GLOBAL_Control
0x140044fcf  cmp     cs:WPP_GLOBAL_Control, rax
0x140044fd6  jz      loc_140045129
0x140044fdc  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140044fe3  test    rcx, rcx
0x140044fe6  jz      loc_140045129
0x140044fec  test    byte ptr [rcx+1Ch], 20h
0x140044ff0  jz      loc_140045129
0x140044ff6  cmp     byte ptr [rcx+19h], 3
0x140044ffa  jb      loc_140045129
0x140045000  mov     rcx, [rcx+10h]
0x140045004  lea     edx, [r14+18h]
0x140045008  lea     r8, WPP_025da0f6f4563439d7f6acd58192d4f6_Traceguids
0x14004500f  call    WPP_SF_
0x140045014  jmp     loc_140045129
0x140045019  mov     r9b, 1; unsigned __int8
0x14004501c  lea     r8, [rbp+arg_0]; unsigned __int8 *
0x140045020  lea     rdx, [rbp+arg_8]; struct DfsFolderReferralData **
0x140045024  lea     r13, [rcx+128h]
0x14004502b  call    ?GetReferralData@DfsFolder@@QEAAKPEAPEAVDfsFolderReferralData@@PEAEE@Z; DfsFolder::GetReferralData(DfsFolderReferralData * *,uchar *,uchar)
0x140045030  test    eax, eax
0x140045032  jnz     loc_1400450DF
0x140045038  mov     rdi, [rbp+arg_8]
0x14004503c  lea     ecx, [rax+3]
0x14004503f  mov     r15d, [rdi+28h]
0x140045043  call    ?DfsGetLocalMachineName@@YAPEBGW4DFS_HOST_NAME_TYPE@CLocalMachine@@@Z; DfsGetLocalMachineName(CLocalMachine::DFS_HOST_NAME_TYPE)
0x140045048  mov     rdx, rax; SourceString
0x14004504b  lea     rcx, [rbp+DestinationString]; DestinationString
0x14004504f  call    cs:__imp_RtlInitUnicodeStringEx
0x140045056  nop     dword ptr [rax+rax+00h]
0x14004505b  xor     esi, esi
0x14004505d  cmp     [rdi+28h], esi
0x140045060  jbe     short loc_1400450D7
0x140045062  mov     eax, esi
0x140045064  lea     rdx, [rbp+DestinationString]; String2
0x140045068  imul    rcx, rax, 38h ; '8'
0x14004506c  mov     rax, [rdi+30h]
0x140045070  mov     r8b, 1; CaseInsensitive
0x140045073  mov     rbx, [rcx+rax+10h]
0x140045078  lea     rcx, [rbx+18h]; String1
0x14004507c  call    cs:__imp_RtlCompareUnicodeString
0x140045083  nop     dword ptr [rax+rax+00h]
0x140045088  test    eax, eax
0x14004508a  jz      short loc_1400450D0
0x14004508c  mov     r9, [r13+8]
0x140045090  lea     rcx, [rbp+var_20]
0x140045094  mov     r8, [rbx+20h]
0x140045098  mov     edx, 2
0x14004509d  call    DfsCreateUnicodePathString
0x1400450a2  test    eax, eax
0x1400450a4  jnz     short loc_1400450C7
0x1400450a6  lea     rcx, [rbp+var_20]; struct _UNICODE_STRING *
0x1400450aa  call    ?AddRootToSyncrhonize@@YAKPEAU_UNICODE_STRING@@@Z; AddRootToSyncrhonize(_UNICODE_STRING *)
0x1400450af  lea     rcx, [rbp+var_20]
0x1400450b3  mov     ebx, eax
0x1400450b5  call    DfsFreeUnicodeString
0x1400450ba  lea     edx, [r14+1]
0x1400450be  test    ebx, ebx
0x1400450c0  cmovnz  edx, r14d
0x1400450c4  mov     r14d, edx
0x1400450c7  cmp     byte ptr cs:word_140071515+1, 1
0x1400450ce  jz      short loc_1400450D7
0x1400450d0  inc     esi
0x1400450d2  cmp     esi, [rdi+28h]
0x1400450d5  jb      short loc_140045062
0x1400450d7  mov     rcx, rdi; this
0x1400450da  call    ?ReleaseReference@DfsGeneric@@QEAAJXZ; DfsGeneric::ReleaseReference(void)
0x1400450df  lea     rax, WPP_GLOBAL_Control
0x1400450e6  cmp     cs:WPP_GLOBAL_Control, rax
0x1400450ed  jz      short loc_140045129
0x1400450ef  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400450f6  test    rcx, rcx
0x1400450f9  jz      short loc_140045129
0x1400450fb  test    byte ptr [rcx+1Ch], 20h
0x1400450ff  jz      short loc_140045129
0x140045101  cmp     byte ptr [rcx+19h], 3
0x140045105  jb      short loc_140045129
0x140045107  mov     rcx, [rcx+10h]
0x14004510b  lea     r8, WPP_025da0f6f4563439d7f6acd58192d4f6_Traceguids
0x140045112  mov     edx, 19h
0x140045117  mov     [rsp+50h+var_28], r14d
0x14004511c  mov     r9, r13
0x14004511f  mov     [rsp+50h+var_30], r15d
0x140045124  call    WPP_SF_ZDd
0x140045129  lea     r11, [rsp+50h+var_s0]
0x14004512e  mov     rbx, [r11+40h]
0x140045132  mov     rsi, [r11+48h]
0x140045136  mov     rsp, r11
0x140045139  pop     r15
0x14004513b  pop     r14
0x14004513d  pop     r13
0x14004513f  pop     rdi
0x140045140  pop     rbp
0x140045141  retn
```
