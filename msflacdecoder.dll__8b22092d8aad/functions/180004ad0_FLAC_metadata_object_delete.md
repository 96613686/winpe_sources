# FLAC__metadata_object_delete

- ea: `0x180004ad0`
- end: `0x180004bf8`
- name: `FLAC__metadata_object_delete`
- size: `296`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003320`
- `0x1800035c0`
- `0x18000d6e0`
- `0x18000d770`
- `0x18000d7e0`
- `0x18000da40`
- `0x18002fe68`

## callees

- `0x180004ad0`
- `0x180005790`
- `0x180005860`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004b09`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004b25`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004b80`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004b93`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004ba6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004bbb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004b09`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004b25`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004b80`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004b93`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004ba6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004bbb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004bd4`

## pseudocode

```c
void __fastcall FLAC__metadata_object_delete(_QWORD *a1)
{
  void *v2; // rcx
  void *v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx

  switch ( *(_DWORD *)a1 )
  {
    case 0:
    case 1:
      break;
    case 2:
    case 3:
      v2 = (void *)a1[3];
      if ( v2 )
      {
        free(v2);
        a1[3] = 0;
      }
      break;
    case 4:
      v3 = (void *)a1[3];
      if ( v3 )
      {
        free(v3);
        a1[3] = 0;
      }
      v4 = a1[5];
      if ( v4 )
      {
        vorbiscomment_entry_array_delete_(v4, *((unsigned int *)a1 + 8));
        a1[5] = 0;
        *((_DWORD *)a1 + 8) = 0;
      }
      break;
    case 5:
      v5 = a1[21];
      if ( v5 )
      {
        cuesheet_track_array_delete_(v5, *((unsigned int *)a1 + 41));
        a1[21] = 0;
        *((_DWORD *)a1 + 41) = 0;
      }
      break;
    case 6:
      v6 = (void *)a1[3];
      if ( v6 )
      {
        free(v6);
        a1[3] = 0;
      }
      v7 = (void *)a1[4];
      if ( v7 )
      {
        free(v7);
        a1[4] = 0;
      }
      v8 = (void *)a1[8];
      if ( v8 )
      {
        free(v8);
        a1[8] = 0;
      }
      break;
    default:
      v9 = (void *)a1[2];
      if ( v9 )
      {
        free(v9);
        a1[2] = 0;
      }
      break;
  }
  free(a1);
}

```

## disassembly

```asm
0x180004ad0  mov     [rsp+arg_0], rbx
0x180004ad5  push    rdi
0x180004ad6  sub     rsp, 20h
0x180004ada  movsxd  rax, dword ptr [rcx]
0x180004add  mov     rbx, rcx
0x180004ae0  cmp     eax, 6; switch 7 cases
0x180004ae3  ja      def_180004AFA; jumptable 0000000180004AFA default case
0x180004ae9  lea     rcx, __ImageBase
0x180004af0  mov     edx, ds:(jpt_180004AFA - 180000000h)[rcx+rax*4]
0x180004af7  add     rdx, rcx
0x180004afa  jmp     rdx; switch jump
0x180004afc  mov     rcx, [rbx+18h]; jumptable 0000000180004AFA cases 2,3
0x180004b00  test    rcx, rcx
0x180004b03  jz      loc_180004BC7; jumptable 0000000180004AFA cases 0,1
0x180004b09  call    cs:__imp_free
0x180004b0f  xor     edi, edi
0x180004b11  mov     [rbx+18h], rdi
0x180004b15  jmp     loc_180004BC7; jumptable 0000000180004AFA cases 0,1
0x180004b1a  mov     rcx, [rbx+18h]; jumptable 0000000180004AFA case 4
0x180004b1e  xor     edi, edi
0x180004b20  test    rcx, rcx
0x180004b23  jz      short loc_180004B2F
0x180004b25  call    cs:__imp_free
0x180004b2b  mov     [rbx+18h], rdi
0x180004b2f  mov     rcx, [rbx+28h]
0x180004b33  test    rcx, rcx
0x180004b36  jz      loc_180004BC7; jumptable 0000000180004AFA cases 0,1
0x180004b3c  mov     edx, [rbx+20h]
0x180004b3f  call    vorbiscomment_entry_array_delete_
0x180004b44  mov     [rbx+28h], rdi
0x180004b48  mov     [rbx+20h], edi
0x180004b4b  jmp     short loc_180004BC7; jumptable 0000000180004AFA cases 0,1
0x180004b4d  mov     rcx, [rbx+0A8h]; jumptable 0000000180004AFA case 5
0x180004b54  test    rcx, rcx
0x180004b57  jz      short loc_180004BC7; jumptable 0000000180004AFA cases 0,1
0x180004b59  mov     edx, [rbx+0A4h]
0x180004b5f  call    cuesheet_track_array_delete_
0x180004b64  xor     edi, edi
0x180004b66  mov     [rbx+0A8h], rdi
0x180004b6d  mov     [rbx+0A4h], edi
0x180004b73  jmp     short loc_180004BC7; jumptable 0000000180004AFA cases 0,1
0x180004b75  mov     rcx, [rbx+18h]; jumptable 0000000180004AFA case 6
0x180004b79  xor     edi, edi
0x180004b7b  test    rcx, rcx
0x180004b7e  jz      short loc_180004B8A
0x180004b80  call    cs:__imp_free
0x180004b86  mov     [rbx+18h], rdi
0x180004b8a  mov     rcx, [rbx+20h]; Block
0x180004b8e  test    rcx, rcx
0x180004b91  jz      short loc_180004B9D
0x180004b93  call    cs:__imp_free
0x180004b99  mov     [rbx+20h], rdi
0x180004b9d  mov     rcx, [rbx+40h]; Block
0x180004ba1  test    rcx, rcx
0x180004ba4  jz      short loc_180004BC7; jumptable 0000000180004AFA cases 0,1
0x180004ba6  call    cs:__imp_free
0x180004bac  mov     [rbx+40h], rdi
0x180004bb0  jmp     short loc_180004BC7; jumptable 0000000180004AFA cases 0,1
0x180004bb2  mov     rcx, [rbx+10h]; jumptable 0000000180004AFA default case
0x180004bb6  test    rcx, rcx
0x180004bb9  jz      short loc_180004BC7; jumptable 0000000180004AFA cases 0,1
0x180004bbb  call    cs:__imp_free
0x180004bc1  xor     edi, edi
0x180004bc3  mov     [rbx+10h], rdi
0x180004bc7  mov     rcx, rbx; jumptable 0000000180004AFA cases 0,1
0x180004bca  mov     rbx, [rsp+28h+arg_0]
0x180004bcf  add     rsp, 20h
0x180004bd3  pop     rdi
0x180004bd4  jmp     cs:__imp_free
```
