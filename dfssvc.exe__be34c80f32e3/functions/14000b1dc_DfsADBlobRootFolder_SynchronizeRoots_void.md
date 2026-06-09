# DfsADBlobRootFolder::SynchronizeRoots(void)

- ea: `0x14000b1dc`
- end: `0x14000b393`
- name: `?SynchronizeRoots@DfsADBlobRootFolder@@QEAAXXZ`
- size: `439`
- prototype: `void __fastcall(DfsADBlobRootFolder *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000acc0`

## callees

- `0x1400096ac`
- `0x14000abc4`
- `0x14000b1dc`
- `0x14000b890`
- `0x1400170d4`
- `0x14003aed4`
- `0x14004a454`
- `0x140058b04`
- `0x140058db8`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x14000b2cc`
- `ntdll!RtlCompareUnicodeString` at `0x14000b2cc`
- `ntdll!RtlInitUnicodeStringEx` at `0x14000b29f`
- `ntdll!RtlInitUnicodeStringEx` at `0x14000b29f`

## pseudocode

```c
void __fastcall DfsADBlobRootFolder::SynchronizeRoots(DfsADBlobRootFolder *this)
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
      WPP_SF_(*((_QWORD *)pWppControl + 2), 22, WPP_03d3ed28a8da3467dc57ccb5cd99db5d_Traceguids);
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
        23,
        (unsigned int)WPP_03d3ed28a8da3467dc57ccb5cd99db5d_Traceguids,
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
0x14000b1dc  mov     [rsp-28h+arg_10], rbx
0x14000b1e1  mov     [rsp-28h+arg_18], rsi
0x14000b1e6  push    rbp
0x14000b1e7  push    rdi
0x14000b1e8  push    r13
0x14000b1ea  push    r14
0x14000b1ec  push    r15
0x14000b1ee  mov     rbp, rsp
0x14000b1f1  sub     rsp, 50h
0x14000b1f5  and     [rbp+arg_8], 0
0x14000b1fa  xor     r14d, r14d
0x14000b1fd  xorps   xmm0, xmm0
0x14000b200  mov     [rbp+arg_0], r14b
0x14000b204  xor     r15d, r15d
0x14000b207  cmp     byte ptr [rcx+1C0h], 1
0x14000b20e  movups  xmmword ptr [rbp+var_20.Length], xmm0
0x14000b212  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000b216  jnz     short loc_14000B269
0x14000b218  lea     rax, WPP_GLOBAL_Control
0x14000b21f  cmp     cs:WPP_GLOBAL_Control, rax
0x14000b226  jz      loc_14000B379
0x14000b22c  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14000b233  test    rcx, rcx
0x14000b236  jz      loc_14000B379
0x14000b23c  test    byte ptr [rcx+1Ch], 20h
0x14000b240  jz      loc_14000B379
0x14000b246  cmp     byte ptr [rcx+19h], 3
0x14000b24a  jb      loc_14000B379
0x14000b250  mov     rcx, [rcx+10h]
0x14000b254  lea     edx, [r14+16h]
0x14000b258  lea     r8, WPP_03d3ed28a8da3467dc57ccb5cd99db5d_Traceguids
0x14000b25f  call    WPP_SF_
0x14000b264  jmp     loc_14000B379
0x14000b269  mov     r9b, 1; unsigned __int8
0x14000b26c  lea     r8, [rbp+arg_0]; unsigned __int8 *
0x14000b270  lea     rdx, [rbp+arg_8]; struct DfsFolderReferralData **
0x14000b274  lea     r13, [rcx+128h]
0x14000b27b  call    ?GetReferralData@DfsFolder@@QEAAKPEAPEAVDfsFolderReferralData@@PEAEE@Z; DfsFolder::GetReferralData(DfsFolderReferralData * *,uchar *,uchar)
0x14000b280  test    eax, eax
0x14000b282  jnz     loc_14000B32F
0x14000b288  mov     rdi, [rbp+arg_8]
0x14000b28c  lea     ecx, [rax+3]
0x14000b28f  mov     r15d, [rdi+28h]
0x14000b293  call    ?DfsGetLocalMachineName@@YAPEBGW4DFS_HOST_NAME_TYPE@CLocalMachine@@@Z; DfsGetLocalMachineName(CLocalMachine::DFS_HOST_NAME_TYPE)
0x14000b298  mov     rdx, rax; SourceString
0x14000b29b  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000b29f  call    cs:__imp_RtlInitUnicodeStringEx
0x14000b2a6  nop     dword ptr [rax+rax+00h]
0x14000b2ab  xor     esi, esi
0x14000b2ad  cmp     [rdi+28h], esi
0x14000b2b0  jbe     short loc_14000B327
0x14000b2b2  mov     eax, esi
0x14000b2b4  lea     rdx, [rbp+DestinationString]; String2
0x14000b2b8  imul    rcx, rax, 38h ; '8'
0x14000b2bc  mov     rax, [rdi+30h]
0x14000b2c0  mov     r8b, 1; CaseInsensitive
0x14000b2c3  mov     rbx, [rcx+rax+10h]
0x14000b2c8  lea     rcx, [rbx+18h]; String1
0x14000b2cc  call    cs:__imp_RtlCompareUnicodeString
0x14000b2d3  nop     dword ptr [rax+rax+00h]
0x14000b2d8  test    eax, eax
0x14000b2da  jz      short loc_14000B320
0x14000b2dc  mov     r9, [r13+8]
0x14000b2e0  lea     rcx, [rbp+var_20]
0x14000b2e4  mov     r8, [rbx+20h]
0x14000b2e8  mov     edx, 2
0x14000b2ed  call    DfsCreateUnicodePathString
0x14000b2f2  test    eax, eax
0x14000b2f4  jnz     short loc_14000B317
0x14000b2f6  lea     rcx, [rbp+var_20]; struct _UNICODE_STRING *
0x14000b2fa  call    ?AddRootToSyncrhonize@@YAKPEAU_UNICODE_STRING@@@Z; AddRootToSyncrhonize(_UNICODE_STRING *)
0x14000b2ff  lea     rcx, [rbp+var_20]
0x14000b303  mov     ebx, eax
0x14000b305  call    DfsFreeUnicodeString
0x14000b30a  lea     edx, [r14+1]
0x14000b30e  test    ebx, ebx
0x14000b310  cmovnz  edx, r14d
0x14000b314  mov     r14d, edx
0x14000b317  cmp     byte ptr cs:word_140071515+1, 1
0x14000b31e  jz      short loc_14000B327
0x14000b320  inc     esi
0x14000b322  cmp     esi, [rdi+28h]
0x14000b325  jb      short loc_14000B2B2
0x14000b327  mov     rcx, rdi; this
0x14000b32a  call    ?ReleaseReference@DfsGeneric@@QEAAJXZ; DfsGeneric::ReleaseReference(void)
0x14000b32f  lea     rax, WPP_GLOBAL_Control
0x14000b336  cmp     cs:WPP_GLOBAL_Control, rax
0x14000b33d  jz      short loc_14000B379
0x14000b33f  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14000b346  test    rcx, rcx
0x14000b349  jz      short loc_14000B379
0x14000b34b  test    byte ptr [rcx+1Ch], 20h
0x14000b34f  jz      short loc_14000B379
0x14000b351  cmp     byte ptr [rcx+19h], 3
0x14000b355  jb      short loc_14000B379
0x14000b357  mov     rcx, [rcx+10h]
0x14000b35b  lea     r8, WPP_03d3ed28a8da3467dc57ccb5cd99db5d_Traceguids
0x14000b362  mov     edx, 17h
0x14000b367  mov     [rsp+50h+var_28], r14d
0x14000b36c  mov     r9, r13
0x14000b36f  mov     [rsp+50h+var_30], r15d
0x14000b374  call    WPP_SF_ZDd
0x14000b379  lea     r11, [rsp+50h+var_s0]
0x14000b37e  mov     rbx, [r11+40h]
0x14000b382  mov     rsi, [r11+48h]
0x14000b386  mov     rsp, r11
0x14000b389  pop     r15
0x14000b38b  pop     r14
0x14000b38d  pop     r13
0x14000b38f  pop     rdi
0x14000b390  pop     rbp
0x14000b391  retn
```
