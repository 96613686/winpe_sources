# CClipRdrPduDispatcher::Initialize(void)

- ea: `0x14002f4a0`
- end: `0x14002f956`
- name: `?Initialize@CClipRdrPduDispatcher@@MEAAJXZ`
- size: `1206`
- prototype: `__int64 __fastcall(CClipRdrPduDispatcher *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x14003f840`

## callees

- `0x140005750`
- `0x1400256b4`
- `0x14002f4a0`
- `0x14006b010`

## string_xrefs

- `0x14002f505`: `Failed to create FORMAT_LIST event source!`
- `0x14002f565`: `Failed to create FORMAT_LIST_RESPONSE event source!`
- `0x14002f5c5`: `Failed to create FORMAT_DATA_REQUEST event source!`
- `0x14002f625`: `Failed to create FORMAT_DATA_RESPONSE event source!`
- `0x14002f685`: `Failed to create CLIP_EVENT_FILE_CONTENTS_REQUEST event source!`
- `0x14002f6e5`: `Failed to create CLIP_EVENT_FILE_CONTENTS_RESPONSE event source!`
- `0x14002f745`: `Failed to create CLIP_CAPS event source!`
- `0x14002f7a5`: `Failed to create CLIP_EVENT_LOCK_CLIPDATA event source!`
- `0x14002f805`: `Failed to create CLIP_EVENT_UNLOCK_CLIPDATA event source!`
- `0x14002f868`: `Failed to create DATA_CHANNEL_REQUEST event source!`
- `0x14002f8cb`: `Failed to create DATA_CHANNEL_RESPONSE event source!`
- `0x14002f91f`: `Failed to create UNKNOWN_PDU event source!`

## pseudocode

```c
__int64 __fastcall CClipRdrPduDispatcher::Initialize(CClipRdrPduDispatcher *this)
{
  int v2; // ebx
  int ActivityIdPrefix; // eax
  int v4; // edx
  const char *v5; // rcx
  int v7; // [rsp+28h] [rbp-10h]

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
    v7 = v2;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v4,
      (unsigned int)WPP_7a491f7304133d177a3768910ae7ce81_Traceguids,
      ActivityIdPrefix,
      (__int64)v5,
      v7);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14002f4a0  mov     [rsp+arg_0], rbx
0x14002f4a5  push    rdi
0x14002f4a6  sub     rsp, 30h
0x14002f4aa  mov     rdi, rcx
0x14002f4ad  or      dword ptr [rcx+14h], 2
0x14002f4b1  lea     r8, [rdi+38h]
0x14002f4b5  mov     rcx, [rcx+30h]
0x14002f4b9  mov     edx, 9Bh
0x14002f4be  mov     rax, [rcx]
0x14002f4c1  mov     rax, [rax+38h]
0x14002f4c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f4ca  mov     ebx, eax
0x14002f4cc  test    eax, eax
0x14002f4ce  jns     short loc_14002F511
0x14002f4d0  mov     rax, cs:WPP_GLOBAL_Control
0x14002f4d7  lea     rcx, WPP_GLOBAL_Control
0x14002f4de  cmp     rax, rcx
0x14002f4e1  jz      loc_14002F949
0x14002f4e7  test    byte ptr [rax+1Ch], 8
0x14002f4eb  jz      loc_14002F949
0x14002f4f1  cmp     byte ptr [rax+19h], 2
0x14002f4f5  jb      loc_14002F949
0x14002f4fb  call    RdpX_GetActivityIdPrefix
0x14002f500  mov     edx, 2Eh ; '.'
0x14002f505  lea     rcx, aFailedToCreate_14; "Failed to create FORMAT_LIST event sour"...
0x14002f50c  jmp     loc_14002F926
0x14002f511  mov     rcx, [rdi+30h]
0x14002f515  lea     r8, [rdi+40h]
0x14002f519  mov     edx, 9Ch
0x14002f51e  mov     rax, [rcx]
0x14002f521  mov     rax, [rax+38h]
0x14002f525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f52a  mov     ebx, eax
0x14002f52c  test    eax, eax
0x14002f52e  jns     short loc_14002F571
0x14002f530  mov     rax, cs:WPP_GLOBAL_Control
0x14002f537  lea     rcx, WPP_GLOBAL_Control
0x14002f53e  cmp     rax, rcx
0x14002f541  jz      loc_14002F949
0x14002f547  test    byte ptr [rax+1Ch], 8
0x14002f54b  jz      loc_14002F949
0x14002f551  cmp     byte ptr [rax+19h], 2
0x14002f555  jb      loc_14002F949
0x14002f55b  call    RdpX_GetActivityIdPrefix
0x14002f560  mov     edx, 2Fh ; '/'
0x14002f565  lea     rcx, aFailedToCreate_16; "Failed to create FORMAT_LIST_RESPONSE e"...
0x14002f56c  jmp     loc_14002F926
0x14002f571  mov     rcx, [rdi+30h]
0x14002f575  lea     r8, [rdi+48h]
0x14002f579  mov     edx, 9Dh
0x14002f57e  mov     rax, [rcx]
0x14002f581  mov     rax, [rax+38h]
0x14002f585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f58a  mov     ebx, eax
0x14002f58c  test    eax, eax
0x14002f58e  jns     short loc_14002F5D1
0x14002f590  mov     rax, cs:WPP_GLOBAL_Control
0x14002f597  lea     rcx, WPP_GLOBAL_Control
0x14002f59e  cmp     rax, rcx
0x14002f5a1  jz      loc_14002F949
0x14002f5a7  test    byte ptr [rax+1Ch], 8
0x14002f5ab  jz      loc_14002F949
0x14002f5b1  cmp     byte ptr [rax+19h], 2
0x14002f5b5  jb      loc_14002F949
0x14002f5bb  call    RdpX_GetActivityIdPrefix
0x14002f5c0  mov     edx, 30h ; '0'
0x14002f5c5  lea     rcx, aFailedToCreate_17; "Failed to create FORMAT_DATA_REQUEST ev"...
0x14002f5cc  jmp     loc_14002F926
0x14002f5d1  mov     rcx, [rdi+30h]
0x14002f5d5  lea     r8, [rdi+50h]
0x14002f5d9  mov     edx, 9Eh
0x14002f5de  mov     rax, [rcx]
0x14002f5e1  mov     rax, [rax+38h]
0x14002f5e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f5ea  mov     ebx, eax
0x14002f5ec  test    eax, eax
0x14002f5ee  jns     short loc_14002F631
0x14002f5f0  mov     rax, cs:WPP_GLOBAL_Control
0x14002f5f7  lea     rcx, WPP_GLOBAL_Control
0x14002f5fe  cmp     rax, rcx
0x14002f601  jz      loc_14002F949
0x14002f607  test    byte ptr [rax+1Ch], 8
0x14002f60b  jz      loc_14002F949
0x14002f611  cmp     byte ptr [rax+19h], 2
0x14002f615  jb      loc_14002F949
0x14002f61b  call    RdpX_GetActivityIdPrefix
0x14002f620  mov     edx, 31h ; '1'
0x14002f625  lea     rcx, aFailedToCreate_4; "Failed to create FORMAT_DATA_RESPONSE e"...
0x14002f62c  jmp     loc_14002F926
0x14002f631  mov     rcx, [rdi+30h]
0x14002f635  lea     r8, [rdi+58h]
0x14002f639  mov     edx, 9Fh
0x14002f63e  mov     rax, [rcx]
0x14002f641  mov     rax, [rax+38h]
0x14002f645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f64a  mov     ebx, eax
0x14002f64c  test    eax, eax
0x14002f64e  jns     short loc_14002F691
0x14002f650  mov     rax, cs:WPP_GLOBAL_Control
0x14002f657  lea     rcx, WPP_GLOBAL_Control
0x14002f65e  cmp     rax, rcx
0x14002f661  jz      loc_14002F949
0x14002f667  test    byte ptr [rax+1Ch], 8
0x14002f66b  jz      loc_14002F949
0x14002f671  cmp     byte ptr [rax+19h], 2
0x14002f675  jb      loc_14002F949
0x14002f67b  call    RdpX_GetActivityIdPrefix
0x14002f680  mov     edx, 32h ; '2'
0x14002f685  lea     rcx, aFailedToCreate_12; "Failed to create CLIP_EVENT_FILE_CONTEN"...
0x14002f68c  jmp     loc_14002F926
0x14002f691  mov     rcx, [rdi+30h]
0x14002f695  lea     r8, [rdi+60h]
0x14002f699  mov     edx, 0A0h
0x14002f69e  mov     rax, [rcx]
0x14002f6a1  mov     rax, [rax+38h]
0x14002f6a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f6aa  mov     ebx, eax
0x14002f6ac  test    eax, eax
0x14002f6ae  jns     short loc_14002F6F1
0x14002f6b0  mov     rax, cs:WPP_GLOBAL_Control
0x14002f6b7  lea     rcx, WPP_GLOBAL_Control
0x14002f6be  cmp     rax, rcx
0x14002f6c1  jz      loc_14002F949
0x14002f6c7  test    byte ptr [rax+1Ch], 8
0x14002f6cb  jz      loc_14002F949
0x14002f6d1  cmp     byte ptr [rax+19h], 2
0x14002f6d5  jb      loc_14002F949
0x14002f6db  call    RdpX_GetActivityIdPrefix
0x14002f6e0  mov     edx, 33h ; '3'
0x14002f6e5  lea     rcx, aFailedToCreate_7; "Failed to create CLIP_EVENT_FILE_CONTEN"...
0x14002f6ec  jmp     loc_14002F926
0x14002f6f1  mov     rcx, [rdi+30h]
0x14002f6f5  lea     r8, [rdi+68h]
0x14002f6f9  mov     edx, 0A1h
0x14002f6fe  mov     rax, [rcx]
0x14002f701  mov     rax, [rax+38h]
0x14002f705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f70a  mov     ebx, eax
0x14002f70c  test    eax, eax
0x14002f70e  jns     short loc_14002F751
0x14002f710  mov     rax, cs:WPP_GLOBAL_Control
0x14002f717  lea     rcx, WPP_GLOBAL_Control
0x14002f71e  cmp     rax, rcx
0x14002f721  jz      loc_14002F949
0x14002f727  test    byte ptr [rax+1Ch], 8
0x14002f72b  jz      loc_14002F949
0x14002f731  cmp     byte ptr [rax+19h], 2
0x14002f735  jb      loc_14002F949
0x14002f73b  call    RdpX_GetActivityIdPrefix
0x14002f740  mov     edx, 34h ; '4'
0x14002f745  lea     rcx, aFailedToCreate; "Failed to create CLIP_CAPS event source"...
0x14002f74c  jmp     loc_14002F926
0x14002f751  mov     rcx, [rdi+30h]
0x14002f755  lea     r8, [rdi+70h]
0x14002f759  mov     edx, 0A4h
0x14002f75e  mov     rax, [rcx]
0x14002f761  mov     rax, [rax+38h]
0x14002f765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f76a  mov     ebx, eax
0x14002f76c  test    eax, eax
0x14002f76e  jns     short loc_14002F7B1
0x14002f770  mov     rax, cs:WPP_GLOBAL_Control
0x14002f777  lea     rcx, WPP_GLOBAL_Control
0x14002f77e  cmp     rax, rcx
0x14002f781  jz      loc_14002F949
0x14002f787  test    byte ptr [rax+1Ch], 8
0x14002f78b  jz      loc_14002F949
0x14002f791  cmp     byte ptr [rax+19h], 2
0x14002f795  jb      loc_14002F949
0x14002f79b  call    RdpX_GetActivityIdPrefix
0x14002f7a0  mov     edx, 35h ; '5'
0x14002f7a5  lea     rcx, aFailedToCreate_15; "Failed to create CLIP_EVENT_LOCK_CLIPDA"...
0x14002f7ac  jmp     loc_14002F926
0x14002f7b1  mov     rcx, [rdi+30h]
0x14002f7b5  lea     r8, [rdi+78h]
0x14002f7b9  mov     edx, 0A5h
0x14002f7be  mov     rax, [rcx]
0x14002f7c1  mov     rax, [rax+38h]
0x14002f7c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f7ca  mov     ebx, eax
0x14002f7cc  test    eax, eax
0x14002f7ce  jns     short loc_14002F811
0x14002f7d0  mov     rax, cs:WPP_GLOBAL_Control
0x14002f7d7  lea     rcx, WPP_GLOBAL_Control
0x14002f7de  cmp     rax, rcx
0x14002f7e1  jz      loc_14002F949
0x14002f7e7  test    byte ptr [rax+1Ch], 8
0x14002f7eb  jz      loc_14002F949
0x14002f7f1  cmp     byte ptr [rax+19h], 2
0x14002f7f5  jb      loc_14002F949
0x14002f7fb  call    RdpX_GetActivityIdPrefix
0x14002f800  mov     edx, 36h ; '6'
0x14002f805  lea     rcx, aFailedToCreate_1; "Failed to create CLIP_EVENT_UNLOCK_CLIP"...
0x14002f80c  jmp     loc_14002F926
0x14002f811  mov     rcx, [rdi+30h]
0x14002f815  lea     r8, [rdi+88h]
0x14002f81c  mov     edx, 0AAh
0x14002f821  mov     rax, [rcx]
0x14002f824  mov     rax, [rax+38h]
0x14002f828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f82d  mov     ebx, eax
0x14002f82f  test    eax, eax
0x14002f831  jns     short loc_14002F874
0x14002f833  mov     rax, cs:WPP_GLOBAL_Control
0x14002f83a  lea     rcx, WPP_GLOBAL_Control
0x14002f841  cmp     rax, rcx
0x14002f844  jz      loc_14002F949
0x14002f84a  test    byte ptr [rax+1Ch], 8
0x14002f84e  jz      loc_14002F949
0x14002f854  cmp     byte ptr [rax+19h], 2
0x14002f858  jb      loc_14002F949
0x14002f85e  call    RdpX_GetActivityIdPrefix
0x14002f863  mov     edx, 37h ; '7'
0x14002f868  lea     rcx, aFailedToCreate_10; "Failed to create DATA_CHANNEL_REQUEST e"...
0x14002f86f  jmp     loc_14002F926
0x14002f874  mov     rcx, [rdi+30h]
0x14002f878  lea     r8, [rdi+90h]
0x14002f87f  mov     edx, 0ABh
0x14002f884  mov     rax, [rcx]
0x14002f887  mov     rax, [rax+38h]
0x14002f88b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f890  mov     ebx, eax
0x14002f892  test    eax, eax
0x14002f894  jns     short loc_14002F8D4
0x14002f896  mov     rax, cs:WPP_GLOBAL_Control
0x14002f89d  lea     rcx, WPP_GLOBAL_Control
0x14002f8a4  cmp     rax, rcx
0x14002f8a7  jz      loc_14002F949
0x14002f8ad  test    byte ptr [rax+1Ch], 8
0x14002f8b1  jz      loc_14002F949
0x14002f8b7  cmp     byte ptr [rax+19h], 2
0x14002f8bb  jb      loc_14002F949
0x14002f8c1  call    RdpX_GetActivityIdPrefix
0x14002f8c6  mov     edx, 38h ; '8'
0x14002f8cb  lea     rcx, aFailedToCreate_9; "Failed to create DATA_CHANNEL_RESPONSE "...
0x14002f8d2  jmp     short loc_14002F926
0x14002f8d4  mov     rcx, [rdi+30h]
0x14002f8d8  lea     r8, [rdi+80h]
0x14002f8df  mov     edx, 0A6h
0x14002f8e4  mov     rax, [rcx]
0x14002f8e7  mov     rax, [rax+38h]
0x14002f8eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f8f0  mov     ebx, eax
0x14002f8f2  test    eax, eax
0x14002f8f4  jns     short loc_14002F949
0x14002f8f6  mov     rax, cs:WPP_GLOBAL_Control
0x14002f8fd  lea     rcx, WPP_GLOBAL_Control
0x14002f904  cmp     rax, rcx
0x14002f907  jz      short loc_14002F949
0x14002f909  test    byte ptr [rax+1Ch], 8
0x14002f90d  jz      short loc_14002F949
0x14002f90f  cmp     byte ptr [rax+19h], 2
0x14002f913  jb      short loc_14002F949
0x14002f915  call    RdpX_GetActivityIdPrefix
0x14002f91a  mov     edx, 39h ; '9'
0x14002f91f  lea     rcx, aFailedToCreate_20; "Failed to create UNKNOWN_PDU event sour"...
0x14002f926  mov     [rsp+38h+var_10], ebx
0x14002f92a  lea     r8, WPP_7a491f7304133d177a3768910ae7ce81_Traceguids
0x14002f931  mov     [rsp+38h+var_18], rcx
0x14002f936  mov     r9d, eax
0x14002f939  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f940  mov     rcx, [rcx+10h]
0x14002f944  call    WPP_SF_DsD
0x14002f949  mov     eax, ebx
0x14002f94b  mov     rbx, [rsp+38h+arg_0]
0x14002f950  add     rsp, 30h
0x14002f954  pop     rdi
0x14002f955  retn
```
