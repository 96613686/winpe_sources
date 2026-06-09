# CClipRdrPduDispatcher::Initialize(void)

- ea: `0x1800cb220`
- end: `0x1800cb6e2`
- name: `?Initialize@CClipRdrPduDispatcher@@MEAAJXZ`
- size: `1218`
- prototype: `__int64 __fastcall(CClipRdrPduDispatcher *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800712a0`

## callees

- `0x18002e600`
- `0x1800cb220`
- `0x18014d010`

## import_xrefs

- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cb27b`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cb2dc`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cb33d`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cb39e`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cb3ff`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cb460`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cb4c1`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cb522`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cb583`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cb5e7`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cb64b`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cb6a0`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cb27b`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cb2dc`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cb33d`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cb39e`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cb3ff`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cb460`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cb4c1`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cb522`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cb583`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cb5e7`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cb64b`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800cb6a0`

## string_xrefs

- `0x1800cb286`: `Failed to create FORMAT_LIST event source!`
- `0x1800cb348`: `Failed to create FORMAT_DATA_REQUEST event source!`
- `0x1800cb2e7`: `Failed to create FORMAT_LIST_RESPONSE event source!`
- `0x1800cb40a`: `Failed to create CLIP_EVENT_FILE_CONTENTS_REQUEST event source!`
- `0x1800cb3a9`: `Failed to create FORMAT_DATA_RESPONSE event source!`
- `0x1800cb4cc`: `Failed to create CLIP_CAPS event source!`
- `0x1800cb46b`: `Failed to create CLIP_EVENT_FILE_CONTENTS_RESPONSE event source!`
- `0x1800cb58e`: `Failed to create CLIP_EVENT_UNLOCK_CLIPDATA event source!`
- `0x1800cb52d`: `Failed to create CLIP_EVENT_LOCK_CLIPDATA event source!`
- `0x1800cb656`: `Failed to create DATA_CHANNEL_RESPONSE event source!`
- `0x1800cb5f2`: `Failed to create DATA_CHANNEL_REQUEST event source!`
- `0x1800cb6ab`: `Failed to create UNKNOWN_PDU event source!`

## pseudocode

```c
__int64 __fastcall CClipRdrPduDispatcher::Initialize(CClipRdrPduDispatcher *this)
{
  int v2; // ebx
  int ActivityIdPrefix; // eax
  int v4; // edx
  const char *v5; // rcx

  *((_DWORD *)this + 5) |= 2u;
  v2 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(**((_QWORD **)this + 6) + 56LL))(
         *((_QWORD *)this + 6),
         155,
         (char *)this + 56);
  if ( v2 >= 0 )
  {
    v2 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(**((_QWORD **)this + 6) + 56LL))(
           *((_QWORD *)this + 6),
           156,
           (char *)this + 64);
    if ( v2 >= 0 )
    {
      v2 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(**((_QWORD **)this + 6) + 56LL))(
             *((_QWORD *)this + 6),
             157,
             (char *)this + 72);
      if ( v2 >= 0 )
      {
        v2 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(**((_QWORD **)this + 6) + 56LL))(
               *((_QWORD *)this + 6),
               158,
               (char *)this + 80);
        if ( v2 >= 0 )
        {
          v2 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(**((_QWORD **)this + 6) + 56LL))(
                 *((_QWORD *)this + 6),
                 159,
                 (char *)this + 88);
          if ( v2 >= 0 )
          {
            v2 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(**((_QWORD **)this + 6) + 56LL))(
                   *((_QWORD *)this + 6),
                   160,
                   (char *)this + 96);
            if ( v2 >= 0 )
            {
              v2 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(**((_QWORD **)this + 6) + 56LL))(
                     *((_QWORD *)this + 6),
                     161,
                     (char *)this + 104);
              if ( v2 >= 0 )
              {
                v2 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(**((_QWORD **)this + 6) + 56LL))(
                       *((_QWORD *)this + 6),
                       164,
                       (char *)this + 112);
                if ( v2 >= 0 )
                {
                  v2 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(**((_QWORD **)this + 6) + 56LL))(
                         *((_QWORD *)this + 6),
                         165,
                         (char *)this + 120);
                  if ( v2 >= 0 )
                  {
                    v2 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(**((_QWORD **)this + 6) + 56LL))(
                           *((_QWORD *)this + 6),
                           170,
                           (char *)this + 136);
                    if ( v2 >= 0 )
                    {
                      v2 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(**((_QWORD **)this + 6) + 56LL))(
                             *((_QWORD *)this + 6),
                             171,
                             (char *)this + 144);
                      if ( v2 >= 0 )
                      {
                        v2 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(**((_QWORD **)this + 6) + 56LL))(
                               *((_QWORD *)this + 6),
                               166,
                               (char *)this + 128);
                        if ( v2 < 0
                          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                        {
                          ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control);
                          v4 = 57;
                          v5 = "Failed to create UNKNOWN_PDU event source!";
                          goto LABEL_61;
                        }
                      }
                      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                      {
                        ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control);
                        v4 = 56;
                        v5 = "Failed to create DATA_CHANNEL_RESPONSE event source!";
                        goto LABEL_61;
                      }
                    }
                    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control);
                      v4 = 55;
                      v5 = "Failed to create DATA_CHANNEL_REQUEST event source!";
                      goto LABEL_61;
                    }
                  }
                  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control);
                    v4 = 54;
                    v5 = "Failed to create CLIP_EVENT_UNLOCK_CLIPDATA event source!";
                    goto LABEL_61;
                  }
                }
                else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                       && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                       && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control);
                  v4 = 53;
                  v5 = "Failed to create CLIP_EVENT_LOCK_CLIPDATA event source!";
                  goto LABEL_61;
                }
              }
              else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                     && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                     && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control);
                v4 = 52;
                v5 = "Failed to create CLIP_CAPS event source!";
                goto LABEL_61;
              }
            }
            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                   && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control);
              v4 = 51;
              v5 = "Failed to create CLIP_EVENT_FILE_CONTENTS_RESPONSE event source!";
              goto LABEL_61;
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control);
            v4 = 50;
            v5 = "Failed to create CLIP_EVENT_FILE_CONTENTS_REQUEST event source!";
            goto LABEL_61;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control);
          v4 = 49;
          v5 = "Failed to create FORMAT_DATA_RESPONSE event source!";
          goto LABEL_61;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control);
        v4 = 48;
        v5 = "Failed to create FORMAT_DATA_REQUEST event source!";
        goto LABEL_61;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control);
      v4 = 47;
      v5 = "Failed to create FORMAT_LIST_RESPONSE event source!";
      goto LABEL_61;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control);
    v4 = 46;
    v5 = "Failed to create FORMAT_LIST event source!";
LABEL_61:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v4,
      (unsigned int)WPP_7a491f7304133d177a3768910ae7ce81_Traceguids,
      ActivityIdPrefix,
      (__int64)v5,
      v2);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800cb220  mov     [rsp+arg_0], rbx
0x1800cb225  push    rdi
0x1800cb226  sub     rsp, 30h
0x1800cb22a  mov     rdi, rcx
0x1800cb22d  or      dword ptr [rcx+14h], 2
0x1800cb231  lea     r8, [rdi+38h]
0x1800cb235  mov     rcx, [rcx+30h]
0x1800cb239  mov     edx, 9Bh
0x1800cb23e  mov     rax, [rcx]
0x1800cb241  mov     rax, [rax+38h]
0x1800cb245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb24a  mov     ebx, eax
0x1800cb24c  test    eax, eax
0x1800cb24e  jns     short loc_1800CB292
0x1800cb250  mov     rax, cs:WPP_GLOBAL_Control
0x1800cb257  lea     rcx, WPP_GLOBAL_Control
0x1800cb25e  cmp     rax, rcx
0x1800cb261  jz      loc_1800CB6D5
0x1800cb267  test    byte ptr [rax+1Ch], 8
0x1800cb26b  jz      loc_1800CB6D5
0x1800cb271  cmp     byte ptr [rax+19h], 2
0x1800cb275  jb      loc_1800CB6D5
0x1800cb27b  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800cb281  mov     edx, 2Eh ; '.'
0x1800cb286  lea     rcx, aFailedToCreate_51; "Failed to create FORMAT_LIST event sour"...
0x1800cb28d  jmp     loc_1800CB6B2
0x1800cb292  mov     rcx, [rdi+30h]
0x1800cb296  lea     r8, [rdi+40h]
0x1800cb29a  mov     edx, 9Ch
0x1800cb29f  mov     rax, [rcx]
0x1800cb2a2  mov     rax, [rax+38h]
0x1800cb2a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb2ab  mov     ebx, eax
0x1800cb2ad  test    eax, eax
0x1800cb2af  jns     short loc_1800CB2F3
0x1800cb2b1  mov     rax, cs:WPP_GLOBAL_Control
0x1800cb2b8  lea     rcx, WPP_GLOBAL_Control
0x1800cb2bf  cmp     rax, rcx
0x1800cb2c2  jz      loc_1800CB6D5
0x1800cb2c8  test    byte ptr [rax+1Ch], 8
0x1800cb2cc  jz      loc_1800CB6D5
0x1800cb2d2  cmp     byte ptr [rax+19h], 2
0x1800cb2d6  jb      loc_1800CB6D5
0x1800cb2dc  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800cb2e2  mov     edx, 2Fh ; '/'
0x1800cb2e7  lea     rcx, aFailedToCreate_56; "Failed to create FORMAT_LIST_RESPONSE e"...
0x1800cb2ee  jmp     loc_1800CB6B2
0x1800cb2f3  mov     rcx, [rdi+30h]
0x1800cb2f7  lea     r8, [rdi+48h]
0x1800cb2fb  mov     edx, 9Dh
0x1800cb300  mov     rax, [rcx]
0x1800cb303  mov     rax, [rax+38h]
0x1800cb307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb30c  mov     ebx, eax
0x1800cb30e  test    eax, eax
0x1800cb310  jns     short loc_1800CB354
0x1800cb312  mov     rax, cs:WPP_GLOBAL_Control
0x1800cb319  lea     rcx, WPP_GLOBAL_Control
0x1800cb320  cmp     rax, rcx
0x1800cb323  jz      loc_1800CB6D5
0x1800cb329  test    byte ptr [rax+1Ch], 8
0x1800cb32d  jz      loc_1800CB6D5
0x1800cb333  cmp     byte ptr [rax+19h], 2
0x1800cb337  jb      loc_1800CB6D5
0x1800cb33d  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800cb343  mov     edx, 30h ; '0'
0x1800cb348  lea     rcx, aFailedToCreate_58; "Failed to create FORMAT_DATA_REQUEST ev"...
0x1800cb34f  jmp     loc_1800CB6B2
0x1800cb354  mov     rcx, [rdi+30h]
0x1800cb358  lea     r8, [rdi+50h]
0x1800cb35c  mov     edx, 9Eh
0x1800cb361  mov     rax, [rcx]
0x1800cb364  mov     rax, [rax+38h]
0x1800cb368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb36d  mov     ebx, eax
0x1800cb36f  test    eax, eax
0x1800cb371  jns     short loc_1800CB3B5
0x1800cb373  mov     rax, cs:WPP_GLOBAL_Control
0x1800cb37a  lea     rcx, WPP_GLOBAL_Control
0x1800cb381  cmp     rax, rcx
0x1800cb384  jz      loc_1800CB6D5
0x1800cb38a  test    byte ptr [rax+1Ch], 8
0x1800cb38e  jz      loc_1800CB6D5
0x1800cb394  cmp     byte ptr [rax+19h], 2
0x1800cb398  jb      loc_1800CB6D5
0x1800cb39e  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800cb3a4  mov     edx, 31h ; '1'
0x1800cb3a9  lea     rcx, aFailedToCreate_21; "Failed to create FORMAT_DATA_RESPONSE e"...
0x1800cb3b0  jmp     loc_1800CB6B2
0x1800cb3b5  mov     rcx, [rdi+30h]
0x1800cb3b9  lea     r8, [rdi+58h]
0x1800cb3bd  mov     edx, 9Fh
0x1800cb3c2  mov     rax, [rcx]
0x1800cb3c5  mov     rax, [rax+38h]
0x1800cb3c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb3ce  mov     ebx, eax
0x1800cb3d0  test    eax, eax
0x1800cb3d2  jns     short loc_1800CB416
0x1800cb3d4  mov     rax, cs:WPP_GLOBAL_Control
0x1800cb3db  lea     rcx, WPP_GLOBAL_Control
0x1800cb3e2  cmp     rax, rcx
0x1800cb3e5  jz      loc_1800CB6D5
0x1800cb3eb  test    byte ptr [rax+1Ch], 8
0x1800cb3ef  jz      loc_1800CB6D5
0x1800cb3f5  cmp     byte ptr [rax+19h], 2
0x1800cb3f9  jb      loc_1800CB6D5
0x1800cb3ff  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800cb405  mov     edx, 32h ; '2'
0x1800cb40a  lea     rcx, aFailedToCreate_47; "Failed to create CLIP_EVENT_FILE_CONTEN"...
0x1800cb411  jmp     loc_1800CB6B2
0x1800cb416  mov     rcx, [rdi+30h]
0x1800cb41a  lea     r8, [rdi+60h]
0x1800cb41e  mov     edx, 0A0h
0x1800cb423  mov     rax, [rcx]
0x1800cb426  mov     rax, [rax+38h]
0x1800cb42a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb42f  mov     ebx, eax
0x1800cb431  test    eax, eax
0x1800cb433  jns     short loc_1800CB477
0x1800cb435  mov     rax, cs:WPP_GLOBAL_Control
0x1800cb43c  lea     rcx, WPP_GLOBAL_Control
0x1800cb443  cmp     rax, rcx
0x1800cb446  jz      loc_1800CB6D5
0x1800cb44c  test    byte ptr [rax+1Ch], 8
0x1800cb450  jz      loc_1800CB6D5
0x1800cb456  cmp     byte ptr [rax+19h], 2
0x1800cb45a  jb      loc_1800CB6D5
0x1800cb460  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800cb466  mov     edx, 33h ; '3'
0x1800cb46b  lea     rcx, aFailedToCreate_33; "Failed to create CLIP_EVENT_FILE_CONTEN"...
0x1800cb472  jmp     loc_1800CB6B2
0x1800cb477  mov     rcx, [rdi+30h]
0x1800cb47b  lea     r8, [rdi+68h]
0x1800cb47f  mov     edx, 0A1h
0x1800cb484  mov     rax, [rcx]
0x1800cb487  mov     rax, [rax+38h]
0x1800cb48b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb490  mov     ebx, eax
0x1800cb492  test    eax, eax
0x1800cb494  jns     short loc_1800CB4D8
0x1800cb496  mov     rax, cs:WPP_GLOBAL_Control
0x1800cb49d  lea     rcx, WPP_GLOBAL_Control
0x1800cb4a4  cmp     rax, rcx
0x1800cb4a7  jz      loc_1800CB6D5
0x1800cb4ad  test    byte ptr [rax+1Ch], 8
0x1800cb4b1  jz      loc_1800CB6D5
0x1800cb4b7  cmp     byte ptr [rax+19h], 2
0x1800cb4bb  jb      loc_1800CB6D5
0x1800cb4c1  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800cb4c7  mov     edx, 34h ; '4'
0x1800cb4cc  lea     rcx, aFailedToCreate_13; "Failed to create CLIP_CAPS event source"...
0x1800cb4d3  jmp     loc_1800CB6B2
0x1800cb4d8  mov     rcx, [rdi+30h]
0x1800cb4dc  lea     r8, [rdi+70h]
0x1800cb4e0  mov     edx, 0A4h
0x1800cb4e5  mov     rax, [rcx]
0x1800cb4e8  mov     rax, [rax+38h]
0x1800cb4ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb4f1  mov     ebx, eax
0x1800cb4f3  test    eax, eax
0x1800cb4f5  jns     short loc_1800CB539
0x1800cb4f7  mov     rax, cs:WPP_GLOBAL_Control
0x1800cb4fe  lea     rcx, WPP_GLOBAL_Control
0x1800cb505  cmp     rax, rcx
0x1800cb508  jz      loc_1800CB6D5
0x1800cb50e  test    byte ptr [rax+1Ch], 8
0x1800cb512  jz      loc_1800CB6D5
0x1800cb518  cmp     byte ptr [rax+19h], 2
0x1800cb51c  jb      loc_1800CB6D5
0x1800cb522  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800cb528  mov     edx, 35h ; '5'
0x1800cb52d  lea     rcx, aFailedToCreate_54; "Failed to create CLIP_EVENT_LOCK_CLIPDA"...
0x1800cb534  jmp     loc_1800CB6B2
0x1800cb539  mov     rcx, [rdi+30h]
0x1800cb53d  lea     r8, [rdi+78h]
0x1800cb541  mov     edx, 0A5h
0x1800cb546  mov     rax, [rcx]
0x1800cb549  mov     rax, [rax+38h]
0x1800cb54d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb552  mov     ebx, eax
0x1800cb554  test    eax, eax
0x1800cb556  jns     short loc_1800CB59A
0x1800cb558  mov     rax, cs:WPP_GLOBAL_Control
0x1800cb55f  lea     rcx, WPP_GLOBAL_Control
0x1800cb566  cmp     rax, rcx
0x1800cb569  jz      loc_1800CB6D5
0x1800cb56f  test    byte ptr [rax+1Ch], 8
0x1800cb573  jz      loc_1800CB6D5
0x1800cb579  cmp     byte ptr [rax+19h], 2
0x1800cb57d  jb      loc_1800CB6D5
0x1800cb583  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800cb589  mov     edx, 36h ; '6'
0x1800cb58e  lea     rcx, aFailedToCreate_17; "Failed to create CLIP_EVENT_UNLOCK_CLIP"...
0x1800cb595  jmp     loc_1800CB6B2
0x1800cb59a  mov     rcx, [rdi+30h]
0x1800cb59e  lea     r8, [rdi+88h]
0x1800cb5a5  mov     edx, 0AAh
0x1800cb5aa  mov     rax, [rcx]
0x1800cb5ad  mov     rax, [rax+38h]
0x1800cb5b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb5b6  mov     ebx, eax
0x1800cb5b8  test    eax, eax
0x1800cb5ba  jns     short loc_1800CB5FE
0x1800cb5bc  mov     rax, cs:WPP_GLOBAL_Control
0x1800cb5c3  lea     rcx, WPP_GLOBAL_Control
0x1800cb5ca  cmp     rax, rcx
0x1800cb5cd  jz      loc_1800CB6D5
0x1800cb5d3  test    byte ptr [rax+1Ch], 8
0x1800cb5d7  jz      loc_1800CB6D5
0x1800cb5dd  cmp     byte ptr [rax+19h], 2
0x1800cb5e1  jb      loc_1800CB6D5
0x1800cb5e7  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800cb5ed  mov     edx, 37h ; '7'
0x1800cb5f2  lea     rcx, aFailedToCreate_43; "Failed to create DATA_CHANNEL_REQUEST e"...
0x1800cb5f9  jmp     loc_1800CB6B2
0x1800cb5fe  mov     rcx, [rdi+30h]
0x1800cb602  lea     r8, [rdi+90h]
0x1800cb609  mov     edx, 0ABh
0x1800cb60e  mov     rax, [rcx]
0x1800cb611  mov     rax, [rax+38h]
0x1800cb615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb61a  mov     ebx, eax
0x1800cb61c  test    eax, eax
0x1800cb61e  jns     short loc_1800CB65F
0x1800cb620  mov     rax, cs:WPP_GLOBAL_Control
0x1800cb627  lea     rcx, WPP_GLOBAL_Control
0x1800cb62e  cmp     rax, rcx
0x1800cb631  jz      loc_1800CB6D5
0x1800cb637  test    byte ptr [rax+1Ch], 8
0x1800cb63b  jz      loc_1800CB6D5
0x1800cb641  cmp     byte ptr [rax+19h], 2
0x1800cb645  jb      loc_1800CB6D5
0x1800cb64b  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800cb651  mov     edx, 38h ; '8'
0x1800cb656  lea     rcx, aFailedToCreate_40; "Failed to create DATA_CHANNEL_RESPONSE "...
0x1800cb65d  jmp     short loc_1800CB6B2
0x1800cb65f  mov     rcx, [rdi+30h]
0x1800cb663  lea     r8, [rdi+80h]
0x1800cb66a  mov     edx, 0A6h
0x1800cb66f  mov     rax, [rcx]
0x1800cb672  mov     rax, [rax+38h]
0x1800cb676  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb67b  mov     ebx, eax
0x1800cb67d  test    eax, eax
0x1800cb67f  jns     short loc_1800CB6D5
0x1800cb681  mov     rax, cs:WPP_GLOBAL_Control
0x1800cb688  lea     rcx, WPP_GLOBAL_Control
0x1800cb68f  cmp     rax, rcx
0x1800cb692  jz      short loc_1800CB6D5
0x1800cb694  test    byte ptr [rax+1Ch], 8
0x1800cb698  jz      short loc_1800CB6D5
0x1800cb69a  cmp     byte ptr [rax+19h], 2
0x1800cb69e  jb      short loc_1800CB6D5
0x1800cb6a0  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800cb6a6  mov     edx, 39h ; '9'
0x1800cb6ab  lea     rcx, aFailedToCreate_69; "Failed to create UNKNOWN_PDU event sour"...
0x1800cb6b2  mov     [rsp+38h+var_10], ebx
0x1800cb6b6  lea     r8, WPP_7a491f7304133d177a3768910ae7ce81_Traceguids
0x1800cb6bd  mov     [rsp+38h+var_18], rcx
0x1800cb6c2  mov     r9d, eax
0x1800cb6c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cb6cc  mov     rcx, [rcx+10h]
0x1800cb6d0  call    WPP_SF_DsD
0x1800cb6d5  mov     eax, ebx
0x1800cb6d7  mov     rbx, [rsp+38h+arg_0]
0x1800cb6dc  add     rsp, 30h
0x1800cb6e0  pop     rdi
0x1800cb6e1  retn
```
