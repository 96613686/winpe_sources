# AmCreateMount

- ea: `0x1400150f0`
- end: `0x14001566c`
- name: `AmCreateMount`
- size: `1404`
- prototype: `__int64 __fastcall(struct _MRX_FCB_ *, __int64, struct _UNICODE_STRING *, char, __int128 *, __int64, _BYTE *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140035384`

## callees

- `0x1400150f0`
- `0x140015674`
- `0x140015988`
- `0x1400159cc`
- `0x1400159fc`
- `0x140015a40`
- `0x140015ab8`
- `0x140033dc0`
- `0x14003adc0`
- `0x14003b0c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140015618`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001562e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015618`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001562e`
- `ntoskrnl!ZwClose` at `0x140015551`
- `ntoskrnl!ZwClose` at `0x140015551`
- `ntoskrnl!ZwCreateFile` at `0x14001553b`
- `ntoskrnl!ZwCreateFile` at `0x14001553b`
- `ntoskrnl!ExAllocatePool2` at `0x140015225`
- `ntoskrnl!ExAllocatePool2` at `0x140015225`
- `rdbss!RxAcquireExclusiveFcbResourceInMRx` at `0x140015594`
- `rdbss!RxAcquireExclusiveFcbResourceInMRx` at `0x140015594`
- `rdbss!RxReleaseFcbResourceInMRx` at `0x1400154e6`
- `rdbss!RxReleaseFcbResourceInMRx` at `0x1400154e6`

## string_xrefs

- `0x140015421`: `MountOptions`

## pseudocode

```c
__int64 __fastcall AmCreateMount(
        struct _MRX_FCB_ *a1,
        __int64 a2,
        struct _UNICODE_STRING *a3,
        char a4,
        __int128 *a5,
        __int64 a6,
        _BYTE *a7)
{
  struct _LIST_ENTRY *Flink; // r13
  _QWORD *v8; // rdi
  PFAST_MUTEX FastMutex; // rax
  __int64 v12; // rsi
  NTSTATUS v14; // ebx
  unsigned int v15; // ecx
  unsigned __int16 *v16; // rax
  unsigned __int16 *v17; // rdx
  unsigned __int16 *v18; // rax
  __int128 *v19; // r15
  unsigned int v20; // ecx
  unsigned int v21; // eax
  size_t v22; // r12
  char *Pool2; // rax
  char *EaBuffer; // rsi
  PDEVICE_OBJECT v25; // rcx
  __int64 v26; // rdx
  char *v27; // rbx
  __int64 v28; // rbx
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int128 v32; // xmm1
  __int128 v33; // xmm0
  __int128 v34; // xmm0
  __int128 v35; // xmm1
  _BYTE *v36; // rdi
  int LinkInfo; // eax
  PLARGE_INTEGER AllocationSize; // [rsp+20h] [rbp-91h]
  void *FileHandle; // [rsp+60h] [rbp-51h] BYREF
  __int64 v40; // [rsp+68h] [rbp-49h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-41h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-31h] BYREF
  unsigned __int16 v44; // [rsp+108h] [rbp+57h] BYREF
  ULONG EaLength; // [rsp+110h] [rbp+5Fh]
  char v46; // [rsp+118h] [rbp+67h]

  v46 = a4;
  Flink = a1->Header.FilterContexts.Flink;
  v8 = *(_QWORD **)(a2 + 104);
  FastMutex = a1->Header.FastMutex;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  v12 = *(_QWORD *)&FastMutex->OldIrql;
  v44 = 0;
  FileHandle = (void *)-1LL;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_1fd2e2a3542c3f6b9236c7d5a3294a22_Traceguids);
  if ( !a3 )
    return 3221225485LL;
  v40 = *(_QWORD *)(a2 + 40);
  v14 = PrependDriveLetterToTarget(v40, v12, (_DWORD)a3, (_DWORD)a3, (__int64)&v44);
  if ( v14 >= 0 )
  {
    v15 = 0;
    if ( v8 )
    {
      v16 = (unsigned __int16 *)v8[4];
      if ( v16 && v8[2] )
        v15 = (*v16 + 19) & 0xFFFFFFFC;
      v17 = (unsigned __int16 *)v8[2];
      if ( v17 )
      {
        v18 = (unsigned __int16 *)v8[3];
        if ( v18 )
          v15 += (*v18 + 21) & 0xFFFFFFFC;
        v15 += (*v17 + 21) & 0xFFFFFFFC;
      }
    }
    v19 = a5;
    v20 = v15 + 24;
    v21 = v20 + 88;
    if ( !a5 )
      v21 = v20;
    EaLength = v21 + 4;
    v22 = v21 + 4;
    Pool2 = (char *)ExAllocatePool2(258, v22, 1700881485);
    EaBuffer = Pool2;
    if ( Pool2 )
    {
      v27 = Pool2;
      memset(Pool2, 0, v22);
      if ( v8 )
      {
        if ( v8[2] )
        {
          strcpy(EaBuffer + 8, "UserName");
          EaBuffer[5] = 9;
          memmove(EaBuffer + 18, *(const void **)(v8[2] + 8LL), *(unsigned __int16 *)v8[2]);
          *((_WORD *)EaBuffer + 3) = *(_WORD *)v8[2];
          EaBuffer[4] = 0;
          v28 = (*(unsigned __int16 *)v8[2] + 21) & 0xFFFFFFFC;
          *(_DWORD *)EaBuffer = v28;
          v27 = &EaBuffer[v28];
        }
        if ( v8[3] && v8[2] )
        {
          strcpy(v27 + 8, "Password");
          v27[5] = 9;
          memmove(v27 + 18, *(const void **)(v8[3] + 8LL), *(unsigned __int16 *)v8[3]);
          *((_WORD *)v27 + 3) = *(_WORD *)v8[3];
          v27[4] = 0;
          v29 = (*(unsigned __int16 *)v8[3] + 21) & 0xFFFFFFFC;
          *(_DWORD *)v27 = v29;
          v27 += v29;
        }
        if ( v8[4] && v8[2] )
        {
          strcpy(v27 + 8, "Domain");
          v27[5] = 7;
          memmove(v27 + 16, *(const void **)(v8[4] + 8LL), *(unsigned __int16 *)v8[4]);
          *((_WORD *)v27 + 3) = *(_WORD *)v8[4];
          v27[4] = 0;
          v30 = (*(unsigned __int16 *)v8[4] + 19) & 0xFFFFFFFC;
          *(_DWORD *)v27 = v30;
          v27 += v30;
        }
      }
      strcpy(v27 + 8, "AuthType");
      v31 = v40;
      v27[5] = 11;
      *((_DWORD *)v27 + 5) = *(_DWORD *)(v31 + 156);
      *((_WORD *)v27 + 3) = 4;
      v27[4] = 0;
      *(_DWORD *)v27 = 24;
      if ( v19 )
      {
        v32 = v19[1];
        strcpy(v27 + 32, "MountOptions");
        v33 = *v19;
        *((_DWORD *)v27 + 7) = 4198144;
        *((_OWORD *)v27 + 3) = v33;
        v34 = v19[2];
        *((_OWORD *)v27 + 4) = v32;
        v35 = v19[3];
        *((_OWORD *)v27 + 5) = v34;
        *((_OWORD *)v27 + 6) = v35;
        *((_DWORD *)v27 + 6) = 0;
      }
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = a3;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      ObjectAttributes.Attributes = v46 != 0 ? 576 : 512;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_Z(
          WPP_GLOBAL_Control->AttachedDevice,
          12,
          WPP_1fd2e2a3542c3f6b9236c7d5a3294a22_Traceguids,
          a3,
          AllocationSize);
      v36 = a7;
      if ( !*a7 && Flink )
      {
        RxReleaseFcbResourceInMRx(a1);
        *v36 = 1;
      }
      v14 = ZwCreateFile(
              &FileHandle,
              0x80u,
              &ObjectAttributes,
              &IoStatusBlock,
              0,
              2u,
              7u,
              1u,
              0x88u,
              EaBuffer,
              EaLength);
      if ( v14 >= 0 )
        ZwClose(FileHandle);
      if ( a6 )
      {
        LinkInfo = AmGetLinkInfo(0, (__int64)v36);
        if ( LinkInfo < 0 )
          v14 = LinkInfo;
      }
      AmRemovePrefix(a3, v44);
      if ( Flink && RxAcquireExclusiveFcbResourceInMRx(a1) < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_1fd2e2a3542c3f6b9236c7d5a3294a22_Traceguids);
      }
      else
      {
        if ( v14 >= 0 )
        {
          ExFreePoolWithTag(EaBuffer, 0);
          v25 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0 )
          {
            return (unsigned int)v14;
          }
          v26 = 15;
          goto LABEL_25;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_ZD(
            WPP_GLOBAL_Control->AttachedDevice,
            14,
            (unsigned int)WPP_1fd2e2a3542c3f6b9236c7d5a3294a22_Traceguids,
            (_DWORD)a3,
            v14);
      }
      ExFreePoolWithTag(EaBuffer, 0);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_1fd2e2a3542c3f6b9236c7d5a3294a22_Traceguids);
      v14 = -1073741801;
    }
  }
  v25 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 )
    return (unsigned int)v14;
  v26 = 16;
LABEL_25:
  WPP_SF_(v25->AttachedDevice, v26, WPP_1fd2e2a3542c3f6b9236c7d5a3294a22_Traceguids);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1400150f0  mov     [rsp-8+arg_18], r9b
0x1400150f5  mov     [rsp-8+Fcb], rcx
0x1400150fa  push    rbp
0x1400150fb  push    rbx
0x1400150fc  push    rsi
0x1400150fd  push    rdi
0x1400150fe  push    r12
0x140015100  push    r13
0x140015102  push    r14
0x140015104  push    r15
0x140015106  lea     rbp, [rsp-7]
0x14001510b  sub     rsp, 0B8h
0x140015112  mov     r13, [rcx+38h]
0x140015116  xorps   xmm0, xmm0
0x140015119  mov     rdi, [rdx+68h]
0x14001511d  xor     eax, eax
0x14001511f  mov     rax, [rcx+30h]
0x140015123  mov     r14, r8
0x140015126  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.ObjectName], xmm0
0x14001512a  mov     rbx, rdx
0x14001512d  movups  xmmword ptr [rbp+3Fh+IoStatusBlock], xmm0
0x140015131  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.Length], xmm0
0x140015135  movups  xmmword ptr [rbp+3Fh+ObjectAttributes+1Ch], xmm0
0x140015139  mov     rsi, [rax+30h]
0x14001513d  xor     eax, eax
0x14001513f  mov     [rbp+3Fh+arg_8], ax
0x140015143  mov     [rbp+3Fh+FileHandle], 0FFFFFFFFFFFFFFFFh
0x14001514b  mov     rcx, cs:WPP_GLOBAL_Control
0x140015152  lea     rax, WPP_GLOBAL_Control
0x140015159  cmp     rcx, rax
0x14001515c  jz      short loc_14001517A
0x14001515e  mov     eax, [rcx+2Ch]
0x140015161  test    al, 40h
0x140015163  jz      short loc_14001517A
0x140015165  mov     rcx, [rcx+18h]
0x140015169  lea     r8, WPP_1fd2e2a3542c3f6b9236c7d5a3294a22_Traceguids
0x140015170  mov     edx, 0Ah
0x140015175  call    WPP_SF_
0x14001517a  test    r14, r14
0x14001517d  jnz     short loc_140015189
0x14001517f  mov     eax, 0C000000Dh
0x140015184  jmp     loc_14001529C
0x140015189  mov     rax, [rbx+28h]
0x14001518d  lea     rcx, [rbp+3Fh+arg_8]
0x140015191  mov     [rsp+0F0h+AllocationSize], rcx
0x140015196  mov     r9, r14
0x140015199  mov     rcx, rax
0x14001519c  mov     [rbp+3Fh+var_88], rax
0x1400151a0  mov     rdx, rsi
0x1400151a3  call    PrependDriveLetterToTarget
0x1400151a8  mov     ebx, eax
0x1400151aa  test    eax, eax
0x1400151ac  js      loc_14001526B
0x1400151b2  xor     ecx, ecx
0x1400151b4  mov     r8d, 0FFFFFFFCh
0x1400151ba  test    rdi, rdi
0x1400151bd  jz      short loc_1400151FF
0x1400151bf  mov     rax, [rdi+20h]
0x1400151c3  test    rax, rax
0x1400151c6  jz      short loc_1400151D7
0x1400151c8  cmp     [rdi+10h], rcx
0x1400151cc  jz      short loc_1400151D7
0x1400151ce  movzx   ecx, word ptr [rax]
0x1400151d1  add     ecx, 13h
0x1400151d4  and     ecx, r8d
0x1400151d7  mov     rdx, [rdi+10h]
0x1400151db  test    rdx, rdx
0x1400151de  jz      short loc_1400151FF
0x1400151e0  mov     rax, [rdi+18h]
0x1400151e4  test    rax, rax
0x1400151e7  jz      short loc_1400151F4
0x1400151e9  movzx   eax, word ptr [rax]
0x1400151ec  add     eax, 15h
0x1400151ef  and     eax, r8d
0x1400151f2  add     ecx, eax
0x1400151f4  movzx   eax, word ptr [rdx]
0x1400151f7  add     eax, 15h
0x1400151fa  and     eax, r8d
0x1400151fd  add     ecx, eax
0x1400151ff  mov     r15, [rbp+3Fh+arg_20]
0x140015203  add     ecx, 18h
0x140015206  test    r15, r15
0x140015209  mov     r8d, 6561644Dh
0x14001520f  lea     eax, [rcx+58h]
0x140015212  cmovz   eax, ecx
0x140015215  mov     ecx, 102h
0x14001521a  add     eax, 4
0x14001521d  mov     edx, eax
0x14001521f  mov     [rbp+3Fh+arg_10], eax
0x140015222  mov     r12d, eax
0x140015225  call    cs:__imp_ExAllocatePool2
0x14001522c  nop     dword ptr [rax+rax+00h]
0x140015231  mov     rsi, rax
0x140015234  test    rax, rax
0x140015237  jnz     short loc_1400152B1
0x140015239  mov     rcx, cs:WPP_GLOBAL_Control
0x140015240  lea     rdx, WPP_GLOBAL_Control
0x140015247  cmp     rcx, rdx
0x14001524a  jz      short loc_140015266
0x14001524c  mov     eax, [rcx+2Ch]
0x14001524f  test    al, 2
0x140015251  jz      short loc_140015266
0x140015253  mov     rcx, [rcx+18h]
0x140015257  lea     edx, [rsi+0Bh]
0x14001525a  lea     r8, WPP_1fd2e2a3542c3f6b9236c7d5a3294a22_Traceguids
0x140015261  call    WPP_SF_
0x140015266  mov     ebx, 0C0000017h
0x14001526b  mov     rcx, cs:WPP_GLOBAL_Control
0x140015272  lea     rax, WPP_GLOBAL_Control
0x140015279  cmp     rcx, rax
0x14001527c  jz      short loc_14001529A
0x14001527e  mov     eax, [rcx+2Ch]
0x140015281  test    al, 2
0x140015283  jz      short loc_14001529A
0x140015285  mov     edx, 10h
0x14001528a  mov     rcx, [rcx+18h]
0x14001528e  lea     r8, WPP_1fd2e2a3542c3f6b9236c7d5a3294a22_Traceguids
0x140015295  call    WPP_SF_
0x14001529a  mov     eax, ebx
0x14001529c  add     rsp, 0B8h
0x1400152a3  pop     r15
0x1400152a5  pop     r14
0x1400152a7  pop     r13
0x1400152a9  pop     r12
0x1400152ab  pop     rdi
0x1400152ac  pop     rsi
0x1400152ad  pop     rbx
0x1400152ae  pop     rbp
0x1400152af  retn
0x1400152b1  mov     r8, r12; Size
0x1400152b4  xor     edx, edx; Val
0x1400152b6  mov     rcx, rsi; void *
0x1400152b9  mov     rbx, rsi
0x1400152bc  call    memset
0x1400152c1  xor     r12d, r12d
0x1400152c4  test    rdi, rdi
0x1400152c7  jz      loc_1400153E2
0x1400152cd  cmp     [rdi+10h], r12
0x1400152d1  jz      short loc_140015323
0x1400152d3  movsd   xmm0, qword ptr cs:aUsername; "UserName"
0x1400152db  lea     rcx, [rsi+12h]; void *
0x1400152df  movsd   qword ptr [rsi+8], xmm0
0x1400152e4  mov     al, byte ptr cs:aUsername+8; ""
0x1400152ea  mov     [rsi+10h], al
0x1400152ed  mov     byte ptr [rsi+5], 9
0x1400152f1  mov     rdx, [rdi+10h]
0x1400152f5  movzx   r8d, word ptr [rdx]; Size
0x1400152f9  mov     rdx, [rdx+8]; Src
0x1400152fd  call    memmove
0x140015302  mov     rax, [rdi+10h]
0x140015306  movzx   ecx, word ptr [rax]
0x140015309  mov     [rsi+6], cx
0x14001530d  mov     [rsi+4], r12b
0x140015311  mov     rax, [rdi+10h]
0x140015315  movzx   ebx, word ptr [rax]
0x140015318  add     ebx, 15h
0x14001531b  and     ebx, 0FFFFFFFCh
0x14001531e  mov     [rsi], ebx
0x140015320  add     rbx, rsi
0x140015323  cmp     [rdi+18h], r12
0x140015327  jz      short loc_14001537F
0x140015329  cmp     [rdi+10h], r12
0x14001532d  jz      short loc_14001537F
0x14001532f  movsd   xmm0, qword ptr cs:aPassword; "Password"
0x140015337  lea     rcx, [rbx+12h]; void *
0x14001533b  movsd   qword ptr [rbx+8], xmm0
0x140015340  mov     al, byte ptr cs:aPassword+8; ""
0x140015346  mov     [rbx+10h], al
0x140015349  mov     byte ptr [rbx+5], 9
0x14001534d  mov     rdx, [rdi+18h]
0x140015351  movzx   r8d, word ptr [rdx]; Size
0x140015355  mov     rdx, [rdx+8]; Src
0x140015359  call    memmove
0x14001535e  mov     rax, [rdi+18h]
0x140015362  movzx   ecx, word ptr [rax]
0x140015365  mov     [rbx+6], cx
0x140015369  mov     [rbx+4], r12b
0x14001536d  mov     rax, [rdi+18h]
0x140015371  movzx   eax, word ptr [rax]
0x140015374  add     eax, 15h
0x140015377  and     eax, 0FFFFFFFCh
0x14001537a  mov     [rbx], eax
0x14001537c  add     rbx, rax
0x14001537f  cmp     [rdi+20h], r12
0x140015383  jz      short loc_1400153E2
0x140015385  cmp     [rdi+10h], r12
0x140015389  jz      short loc_1400153E2
0x14001538b  mov     eax, dword ptr cs:aDomain; "Domain"
0x140015391  lea     rcx, [rbx+10h]; void *
0x140015395  mov     [rbx+8], eax
0x140015398  movzx   eax, word ptr cs:aDomain+4; "in"
0x14001539f  mov     [rbx+0Ch], ax
0x1400153a3  mov     al, byte ptr cs:aDomain+6; ""
0x1400153a9  mov     [rbx+0Eh], al
0x1400153ac  mov     byte ptr [rbx+5], 7
0x1400153b0  mov     rdx, [rdi+20h]
0x1400153b4  movzx   r8d, word ptr [rdx]; Size
0x1400153b8  mov     rdx, [rdx+8]; Src
0x1400153bc  call    memmove
0x1400153c1  mov     rax, [rdi+20h]
0x1400153c5  movzx   ecx, word ptr [rax]
0x1400153c8  mov     [rbx+6], cx
0x1400153cc  mov     [rbx+4], r12b
0x1400153d0  mov     rax, [rdi+20h]
0x1400153d4  movzx   eax, word ptr [rax]
0x1400153d7  add     eax, 13h
0x1400153da  and     eax, 0FFFFFFFCh
0x1400153dd  mov     [rbx], eax
0x1400153df  add     rbx, rax
0x1400153e2  movsd   xmm0, qword ptr cs:aAuthtype_0; "AuthType"
0x1400153ea  mov     edx, 4
0x1400153ef  movsd   qword ptr [rbx+8], xmm0
0x1400153f4  mov     al, byte ptr cs:aAuthtype_0+8; ""
0x1400153fa  mov     [rbx+10h], al
0x1400153fd  mov     rax, [rbp+3Fh+var_88]
0x140015401  mov     byte ptr [rbx+5], 0Bh
0x140015405  mov     eax, [rax+9Ch]
0x14001540b  mov     [rbx+14h], eax
0x14001540e  mov     [rbx+6], dx
0x140015412  mov     [rbx+4], r12b
0x140015416  mov     dword ptr [rbx], 18h
0x14001541c  test    r15, r15
0x14001541f  jz      short loc_14001546E
0x140015421  movsd   xmm0, qword ptr cs:Str2; "MountOptions"
0x140015429  movaps  xmm1, xmmword ptr [r15+10h]
0x14001542e  movsd   qword ptr [rbx+20h], xmm0
0x140015433  mov     eax, dword ptr cs:Str2+8; "ions"
0x140015439  movaps  xmm0, xmmword ptr [r15]
0x14001543d  mov     [rbx+28h], eax
0x140015440  mov     al, byte ptr cs:Str2+0Ch; ""
0x140015446  mov     [rbx+2Ch], al
0x140015449  mov     dword ptr [rbx+1Ch], 400F00h
0x140015450  movups  xmmword ptr [rbx+30h], xmm0
0x140015454  movaps  xmm0, xmmword ptr [r15+20h]
0x140015459  movups  xmmword ptr [rbx+40h], xmm1
0x14001545d  movaps  xmm1, xmmword ptr [r15+30h]
0x140015462  movups  xmmword ptr [rbx+50h], xmm0
0x140015466  movups  xmmword ptr [rbx+60h], xmm1
0x14001546a  mov     [rbx+18h], r12d
0x14001546e  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], r12
0x140015472  xorps   xmm0, xmm0
0x140015475  mov     r12b, [rbp+3Fh+arg_18]
0x140015479  mov     al, r12b
0x14001547c  mov     [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x140015483  neg     al
0x140015485  mov     [rbp+3Fh+ObjectAttributes.ObjectName], r14
0x140015489  movdqu  xmmword ptr [rbp+3Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x14001548e  sbb     ecx, ecx
0x140015490  and     ecx, 40h
0x140015493  add     ecx, 200h
0x140015499  mov     [rbp+3Fh+ObjectAttributes.Attributes], ecx
0x14001549c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400154a3  lea     rax, WPP_GLOBAL_Control
0x1400154aa  cmp     rcx, rax
0x1400154ad  jz      short loc_1400154CE
0x1400154af  mov     eax, [rcx+2Ch]
0x1400154b2  test    dl, al
0x1400154b4  jz      short loc_1400154CE
0x1400154b6  mov     rcx, [rcx+18h]
0x1400154ba  lea     r8, WPP_1fd2e2a3542c3f6b9236c7d5a3294a22_Traceguids
0x1400154c1  mov     edx, 0Ch
0x1400154c6  mov     r9, r14
0x1400154c9  call    WPP_SF_Z
0x1400154ce  mov     rdi, [rbp+3Fh+arg_30]
0x1400154d2  mov     r15, [rbp+3Fh+Fcb]
0x1400154d6  cmp     byte ptr [rdi], 0
0x1400154d9  jnz     short loc_1400154F5
0x1400154db  test    r13, r13
0x1400154de  jz      short loc_1400154F5
0x1400154e0  mov     rdx, r13
0x1400154e3  mov     rcx, r15; Fcb
0x1400154e6  call    cs:__imp_RxReleaseFcbResourceInMRx
0x1400154ed  nop     dword ptr [rax+rax+00h]
0x1400154f2  mov     byte ptr [rdi], 1
0x1400154f5  mov     eax, [rbp+3Fh+arg_10]
0x1400154f8  lea     r9, [rbp+3Fh+IoStatusBlock]; IoStatusBlock
0x1400154fc  mov     [rsp+0F0h+EaLength], eax; EaLength
0x140015500  lea     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x140015504  mov     [rsp+0F0h+EaBuffer], rsi; EaBuffer
0x140015509  lea     rcx, [rbp+3Fh+FileHandle]; FileHandle
0x14001550d  mov     [rsp+0F0h+CreateOptions], 88h; CreateOptions
0x140015515  mov     edx, 80h; DesiredAccess
0x14001551a  mov     [rsp+0F0h+CreateDisposition], 1; CreateDisposition
0x140015522  mov     [rsp+0F0h+ShareAccess], 7; ShareAccess
0x14001552a  mov     [rsp+0F0h+FileAttributes], 2; FileAttributes
0x140015532  mov     [rsp+0F0h+AllocationSize], 0; AllocationSize
0x14001553b  call    cs:__imp_ZwCreateFile
0x140015542  nop     dword ptr [rax+rax+00h]
0x140015547  mov     ebx, eax
0x140015549  test    eax, eax
0x14001554b  js      short loc_14001555D
0x14001554d  mov     rcx, [rbp+3Fh+FileHandle]; Handle
0x140015551  call    cs:__imp_ZwClose
0x140015558  nop     dword ptr [rax+rax+00h]
0x14001555d  mov     r9, [rbp+3Fh+arg_28]
0x140015561  test    r9, r9
0x140015564  jz      short loc_14001557D
0x140015566  mov     r8b, r12b
0x140015569  mov     [rsp+0F0h+AllocationSize], rdi; __int64
0x14001556e  mov     rdx, r14
  ... truncated ...
```
