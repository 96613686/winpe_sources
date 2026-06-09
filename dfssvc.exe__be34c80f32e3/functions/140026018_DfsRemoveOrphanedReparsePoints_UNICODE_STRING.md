# DfsRemoveOrphanedReparsePoints(_UNICODE_STRING *)

- ea: `0x140026018`
- end: `0x140026227`
- name: `?DfsRemoveOrphanedReparsePoints@@YAKPEAU_UNICODE_STRING@@@Z`
- size: `527`
- prototype: `unsigned int __fastcall(struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path`

## callers

- `0x140026230`

## callees

- `0x14000f958`
- `0x14002533c`
- `0x1400253d8`
- `0x1400254d8`
- `0x140025734`
- `0x140025f18`
- `0x140026018`
- `0x14002634c`
- `0x1400266f8`
- `0x14005ce70`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400261dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400261f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400261dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400261f2`

## pseudocode

```c
__int64 __fastcall DfsRemoveOrphanedReparsePoints(struct _UNICODE_STRING *a1)
{
  __int64 v1; // rdi
  __int64 i; // rsi
  unsigned int RootsOnVolume; // ebx
  unsigned int VolumeHandleByName; // eax
  int v6; // edx
  int v7; // r8d
  unsigned int v8; // r9d
  unsigned __int8 v10[8]; // [rsp+30h] [rbp-40h] BYREF
  HANDLE v11; // [rsp+38h] [rbp-38h] BYREF
  HANDLE hObject; // [rsp+40h] [rbp-30h] BYREF
  struct _LIST_ENTRY v13; // [rsp+48h] [rbp-28h] BYREF
  __int64 v14[2]; // [rsp+58h] [rbp-18h] BYREF

  v1 = -1;
  hObject = (HANDLE)-1LL;
  i = -1;
  v11 = (HANDLE)-1LL;
  *(_OWORD *)v14 = 0;
  v13 = 0;
  RootsOnVolume = DfsGetRootsOnVolume(a1, &v13);
  if ( RootsOnVolume || v13.Flink == &v13 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && pWppControl
      && (((1 << (RootsOnVolume != 0 ? 11 : 31)) | 0x20) & pWppControl[7]) != 0
      && *((_BYTE *)pWppControl + 25) >= 2u )
    {
      WPP_SF_DZ(
        *((_QWORD *)pWppControl + 2),
        24,
        (unsigned int)WPP_06cdb52cbe4531ba727f9e22c79a690d_Traceguids,
        RootsOnVolume,
        (__int64)a1);
    }
  }
  else
  {
    RootsOnVolume = DfsOpenReparseIndex(a1, &hObject);
    if ( RootsOnVolume )
    {
      v1 = (__int64)hObject;
    }
    else
    {
      VolumeHandleByName = DfsGetVolumeHandleByName(a1, &v11);
      v1 = (__int64)hObject;
      RootsOnVolume = VolumeHandleByName;
      if ( VolumeHandleByName )
      {
        i = (__int64)v11;
      }
      else
      {
        v10[0] = 0;
        RootsOnVolume = DfsGetNextReparseRecord(hObject, (struct _FILE_REPARSE_POINT_INFORMATION *)v14, v10);
        for ( i = (__int64)v11;
              !v10[0];
              RootsOnVolume = DfsGetNextReparseRecord((void *)v1, (struct _FILE_REPARSE_POINT_INFORMATION *)v14, v10) )
        {
          if ( RootsOnVolume )
            break;
          if ( LODWORD(v14[1]) == -2147483638 )
          {
            v8 = DfsRemoveReparseIfOrphaned((void *)i, a1, v14[0], &v13);
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && pWppControl
              && (pWppControl[7] & 0x80000020) != 0
              && *((_BYTE *)pWppControl + 25) >= 2u )
            {
              WPP_SF_DZD(*((_QWORD *)pWppControl + 2), v6, v7, v8, (__int64)a1, v14[0]);
            }
          }
          if ( HIBYTE(word_140071515) == 1 )
            break;
        }
      }
    }
  }
  DfsDereferenceRoots(&v13);
  if ( v1 != -1 )
    CloseHandle((HANDLE)v1);
  if ( i != -1 )
    CloseHandle((HANDLE)i);
  return RootsOnVolume;
}

```

## disassembly

```asm
0x140026018  mov     [rsp-18h+arg_8], rbx
0x14002601d  mov     [rsp-18h+arg_10], rsi
0x140026022  mov     [rsp-18h+arg_18], rdi
0x140026027  push    rbp
0x140026028  push    r14
0x14002602a  push    r15
0x14002602c  mov     rbp, rsp
0x14002602f  sub     rsp, 70h
0x140026033  mov     rax, cs:__security_cookie
0x14002603a  xor     rax, rsp
0x14002603d  mov     [rbp+var_8], rax
0x140026041  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140026045  lea     rdx, [rbp+var_28]; struct _LIST_ENTRY *
0x140026049  xorps   xmm0, xmm0
0x14002604c  mov     [rbp+hObject], rdi
0x140026050  xorps   xmm1, xmm1
0x140026053  or      rsi, rdi
0x140026056  mov     [rbp+var_38], rsi
0x14002605a  mov     r14, rcx
0x14002605d  movups  xmmword ptr [rbp+var_18], xmm0
0x140026061  movups  xmmword ptr [rbp+var_28.Flink], xmm1
0x140026065  call    ?DfsGetRootsOnVolume@@YAKPEAU_UNICODE_STRING@@PEAU_LIST_ENTRY@@@Z; DfsGetRootsOnVolume(_UNICODE_STRING *,_LIST_ENTRY *)
0x14002606a  mov     ebx, eax
0x14002606c  test    eax, eax
0x14002606e  jnz     loc_140026173
0x140026074  lea     rax, [rbp+var_28]
0x140026078  cmp     [rbp+var_28.Flink], rax
0x14002607c  jz      loc_140026173
0x140026082  lea     rdx, [rbp+hObject]; void **
0x140026086  mov     rcx, r14; struct _UNICODE_STRING *
0x140026089  call    ?DfsOpenReparseIndex@@YAKPEAU_UNICODE_STRING@@PEAPEAX@Z; DfsOpenReparseIndex(_UNICODE_STRING *,void * *)
0x14002608e  mov     ebx, eax
0x140026090  test    eax, eax
0x140026092  jnz     loc_14002616D
0x140026098  lea     rdx, [rbp+var_38]; void **
0x14002609c  mov     rcx, r14; struct _UNICODE_STRING *
0x14002609f  call    ?DfsGetVolumeHandleByName@@YAKPEAU_UNICODE_STRING@@PEAPEAX@Z; DfsGetVolumeHandleByName(_UNICODE_STRING *,void * *)
0x1400260a4  mov     rdi, [rbp+hObject]
0x1400260a8  mov     ebx, eax
0x1400260aa  test    eax, eax
0x1400260ac  jnz     loc_140026167
0x1400260b2  lea     r8, [rbp+var_40]; unsigned __int8 *
0x1400260b6  mov     [rbp+var_40], al
0x1400260b9  lea     rdx, [rbp+var_18]; struct _FILE_REPARSE_POINT_INFORMATION *
0x1400260bd  mov     rcx, rdi; void *
0x1400260c0  call    ?DfsGetNextReparseRecord@@YAKPEAXPEAU_FILE_REPARSE_POINT_INFORMATION@@PEAE@Z; DfsGetNextReparseRecord(void *,_FILE_REPARSE_POINT_INFORMATION *,uchar *)
0x1400260c5  cmp     [rbp+var_40], 0
0x1400260c9  mov     ebx, eax
0x1400260cb  mov     rsi, [rbp+var_38]
0x1400260cf  jnz     loc_1400261CB
0x1400260d5  lea     r15, WPP_GLOBAL_Control
0x1400260dc  test    ebx, ebx
0x1400260de  jnz     loc_1400261CB
0x1400260e4  cmp     dword ptr [rbp+var_18+8], 8000000Ah
0x1400260eb  jnz     short loc_14002613C
0x1400260ed  mov     r8, [rbp+var_18]; __int64
0x1400260f1  lea     r9, [rbp+var_28]; struct _LIST_ENTRY *
0x1400260f5  mov     rdx, r14; struct _UNICODE_STRING *
0x1400260f8  mov     rcx, rsi; void *
0x1400260fb  call    ?DfsRemoveReparseIfOrphaned@@YAKPEAXPEAU_UNICODE_STRING@@_JPEAU_LIST_ENTRY@@@Z; DfsRemoveReparseIfOrphaned(void *,_UNICODE_STRING *,__int64,_LIST_ENTRY *)
0x140026100  mov     r9d, eax
0x140026103  cmp     cs:WPP_GLOBAL_Control, r15
0x14002610a  jz      short loc_14002613C
0x14002610c  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140026113  test    rcx, rcx
0x140026116  jz      short loc_14002613C
0x140026118  test    dword ptr [rcx+1Ch], 80000020h
0x14002611f  jz      short loc_14002613C
0x140026121  cmp     byte ptr [rcx+19h], 2
0x140026125  jb      short loc_14002613C
0x140026127  mov     eax, dword ptr [rbp+var_18]
0x14002612a  mov     rcx, [rcx+10h]
0x14002612e  mov     [rsp+70h+var_48], eax
0x140026132  mov     [rsp+70h+var_50], r14
0x140026137  call    WPP_SF_DZD
0x14002613c  cmp     byte ptr cs:word_140071515+1, 1
0x140026143  jz      loc_1400261CB
0x140026149  lea     r8, [rbp+var_40]; unsigned __int8 *
0x14002614d  mov     rcx, rdi; void *
0x140026150  lea     rdx, [rbp+var_18]; struct _FILE_REPARSE_POINT_INFORMATION *
0x140026154  call    ?DfsGetNextReparseRecord@@YAKPEAXPEAU_FILE_REPARSE_POINT_INFORMATION@@PEAE@Z; DfsGetNextReparseRecord(void *,_FILE_REPARSE_POINT_INFORMATION *,uchar *)
0x140026159  cmp     [rbp+var_40], 0
0x14002615d  mov     ebx, eax
0x14002615f  jz      loc_1400260DC
0x140026165  jmp     short loc_1400261CB
0x140026167  mov     rsi, [rbp+var_38]
0x14002616b  jmp     short loc_1400261CB
0x14002616d  mov     rdi, [rbp+hObject]
0x140026171  jmp     short loc_1400261CB
0x140026173  lea     r15, WPP_GLOBAL_Control
0x14002617a  cmp     cs:WPP_GLOBAL_Control, r15
0x140026181  jz      short loc_1400261CB
0x140026183  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14002618a  test    rcx, rcx
0x14002618d  jz      short loc_1400261CB
0x14002618f  mov     eax, ebx
0x140026191  neg     eax
0x140026193  mov     eax, 20h ; ' '
0x140026198  sbb     edx, edx
0x14002619a  and     edx, 0FFFFFFECh
0x14002619d  add     edx, 1Fh
0x1400261a0  bts     eax, edx
0x1400261a3  test    [rcx+1Ch], eax
0x1400261a6  jz      short loc_1400261CB
0x1400261a8  cmp     byte ptr [rcx+19h], 2
0x1400261ac  jb      short loc_1400261CB
0x1400261ae  mov     rcx, [rcx+10h]
0x1400261b2  lea     r8, WPP_06cdb52cbe4531ba727f9e22c79a690d_Traceguids
0x1400261b9  mov     edx, 18h
0x1400261be  mov     [rsp+70h+var_50], r14
0x1400261c3  mov     r9d, ebx
0x1400261c6  call    WPP_SF_DZ
0x1400261cb  lea     rcx, [rbp+var_28]; struct _LIST_ENTRY *
0x1400261cf  call    ?DfsDereferenceRoots@@YAXPEAU_LIST_ENTRY@@@Z; DfsDereferenceRoots(_LIST_ENTRY *)
0x1400261d4  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1400261d8  jz      short loc_1400261E9
0x1400261da  mov     rcx, rdi; hObject
0x1400261dd  call    cs:__imp_CloseHandle
0x1400261e4  nop     dword ptr [rax+rax+00h]
0x1400261e9  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1400261ed  jz      short loc_1400261FE
0x1400261ef  mov     rcx, rsi; hObject
0x1400261f2  call    cs:__imp_CloseHandle
0x1400261f9  nop     dword ptr [rax+rax+00h]
0x1400261fe  mov     eax, ebx
0x140026200  mov     rcx, [rbp+var_8]
0x140026204  xor     rcx, rsp; StackCookie
0x140026207  call    __security_check_cookie
0x14002620c  lea     r11, [rsp+70h+var_s0]
0x140026211  mov     rbx, [r11+28h]
0x140026215  mov     rsi, [r11+30h]
0x140026219  mov     rdi, [r11+38h]
0x14002621d  mov     rsp, r11
0x140026220  pop     r15
0x140026222  pop     r14
0x140026224  pop     rbp
0x140026225  retn
```
