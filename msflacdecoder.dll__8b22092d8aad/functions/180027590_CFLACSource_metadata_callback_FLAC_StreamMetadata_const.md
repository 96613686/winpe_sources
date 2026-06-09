# CFLACSource::metadata_callback(FLAC__StreamMetadata const *)

- ea: `0x180027590`
- end: `0x180027968`
- name: `?metadata_callback@CFLACSource@@UEAAXPEBUFLAC__StreamMetadata@@@Z`
- size: `984`
- prototype: `void __fastcall(CFLACSource *__hidden this, const struct FLAC__StreamMetadata *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800018f0`
- `0x18001c638`
- `0x180021910`
- `0x180021944`
- `0x1800243c8`
- `0x180027590`
- `0x180027b80`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002793f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002793f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027893`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027893`

## pseudocode

```c
void __fastcall CFLACSource::metadata_callback(CFLACSource *this, const struct FLAC__StreamMetadata *a2)
{
  CFLACSource *v4; // rsi
  unsigned int v5; // edx
  int v6; // eax
  __int64 v7; // rdx
  unsigned int v8; // eax
  void *v9; // rcx
  void *v10; // rax
  int i; // r10d
  _BYTE *j; // rcx
  unsigned int v13; // eax
  void *v14; // rax
  void *v15; // rcx
  unsigned __int64 v16; // [rsp+30h] [rbp+8h] BYREF
  char *v17; // [rsp+38h] [rbp+10h]

  v4 = (CFLACSource *)((char *)this - 112);
  v17 = (char *)this - 112;
  if ( !a2 )
    goto LABEL_50;
  v5 = *(_DWORD *)a2;
  if ( dword_18006E1D8 )
  {
    v16 = v5;
    (**((void (__fastcall ***)(char *, __int64, char **))this + 39))((char *)this + 312, 4, (char **)&v16);
  }
  if ( *(_DWORD *)a2 )
  {
    if ( *(_DWORD *)a2 == 3 )
    {
      if ( (*((_BYTE *)this + 277) & 2) != 0 )
      {
        CFLACSource::CleanupSeekTable(v4);
        *((_DWORD *)this + 116) = *((_DWORD *)a2 + 4);
        if ( dword_18006E1D8 )
        {
          v16 = *((unsigned int *)a2 + 4);
          (**((void (__fastcall ***)(char *, __int64, char **))this + 39))((char *)this + 312, 3, (char **)&v16);
        }
        v8 = *((_DWORD *)this + 116);
        if ( !v8 )
          goto LABEL_50;
        v9 = operator new[](saturated_mul(v8, 0x18u));
        *((_QWORD *)this + 59) = v9;
        if ( !v9 )
        {
          if ( !byte_18006E80D )
            goto LABEL_50;
          v7 = 97;
          goto LABEL_9;
        }
        if ( memcpy_s(
               v9,
               24LL * *((unsigned int *)this + 116),
               *((const void *const *)a2 + 3),
               24LL * *((unsigned int *)this + 116)) )
        {
          if ( !byte_18006E80D )
            goto LABEL_50;
          v7 = 98;
          goto LABEL_9;
        }
        v10 = operator new[](saturated_mul(*((unsigned int *)this + 116), 8u));
        *((_QWORD *)this + 33) = v10;
        if ( !v10 )
        {
          if ( !byte_18006E80D )
            goto LABEL_50;
          v7 = 99;
          goto LABEL_9;
        }
        if ( (*((_BYTE *)this + 278) & 1) == 0 )
        {
          if ( !byte_18006E80D )
            goto LABEL_50;
          v7 = 100;
          goto LABEL_9;
        }
        for ( i = 0; i < *((_DWORD *)this + 116); ++i )
          *(_QWORD *)(*((_QWORD *)this + 33) + 8LL * i) = 10000000
                                                        * (*(_QWORD *)(*((_QWORD *)this + 59) + 24LL * i)
                                                         / (unsigned __int64)*((unsigned int *)this + 98));
        *((_BYTE *)this + 278) |= 2u;
      }
    }
    else if ( *(_DWORD *)a2 == 6 && (*((_BYTE *)v4 + 389) & 8) != 0 )
    {
      CFLACSource::CleanupPictureData(v4);
      for ( j = (_BYTE *)*((_QWORD *)a2 + 3); *j; ++j )
      {
        if ( (unsigned __int8)(*j - 32) > 0x5Eu )
        {
          if ( !byte_18006E80D )
            goto LABEL_50;
          v7 = 101;
          goto LABEL_9;
        }
      }
      *((_DWORD *)this + 129) = *((_DWORD *)a2 + 13);
      v13 = *((_DWORD *)a2 + 14);
      *((_DWORD *)this + 130) = v13;
      v14 = CoTaskMemAlloc(v13);
      *((_QWORD *)this + 66) = v14;
      if ( v14 )
      {
        *((_DWORD *)this + 128) = *((_DWORD *)a2 + 12);
        *((_DWORD *)this + 127) = *((_DWORD *)a2 + 11);
        *((_DWORD *)this + 126) = *((_DWORD *)a2 + 10);
        *((_DWORD *)this + 120) = *((_DWORD *)a2 + 4);
        if ( !memcpy_s(
                v14,
                *((unsigned int *)this + 130),
                *((const void *const *)a2 + 8),
                *((unsigned int *)this + 130)) )
        {
          *((_BYTE *)this + 278) |= 8u;
          goto LABEL_47;
        }
        if ( !byte_18006E80D )
          goto LABEL_50;
        v7 = 103;
      }
      else
      {
        if ( !byte_18006E80D )
          goto LABEL_50;
        v7 = 102;
      }
      goto LABEL_9;
    }
LABEL_47:
    *((_DWORD *)this + 70) += *((_DWORD *)a2 + 2);
    if ( *((_DWORD *)a2 + 1) )
    {
      v15 = (void *)*((_QWORD *)this + 36);
      if ( v15 )
        SetEvent(v15);
    }
    goto LABEL_50;
  }
  if ( (*((_BYTE *)this + 277) & 1) == 0 )
    goto LABEL_47;
  *((_QWORD *)this + 51) = *((_QWORD *)a2 + 6);
  v6 = *((_DWORD *)a2 + 8);
  if ( v6 )
  {
    *((_DWORD *)this + 98) = v6;
    *((_DWORD *)this + 99) = *((_DWORD *)a2 + 9);
    *((_DWORD *)this + 100) = *((_DWORD *)a2 + 10);
    *((_DWORD *)this + 94) = *((_DWORD *)a2 + 4);
    *((_DWORD *)this + 95) = *((_DWORD *)a2 + 5);
    *((_DWORD *)this + 96) = *((_DWORD *)a2 + 6);
    *((_DWORD *)this + 97) = *((_DWORD *)a2 + 7);
    *((_BYTE *)this + 278) |= 1u;
    if ( dword_18006E1D8 )
    {
      v16 = (unsigned __int64)this + 376;
      (**((void (__fastcall ***)(char *, __int64, char **))this + 39))((char *)this + 312, 2, (char **)&v16);
    }
    goto LABEL_47;
  }
  if ( byte_18006E80D )
  {
    v7 = 96;
LABEL_9:
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), v7, &WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids);
  }
LABEL_50:
  CFLACSourceTelemetry::MetadataTypeSet((CFLACSource *)((char *)this + 312), *((_BYTE *)this + 278));
}

```

## disassembly

```asm
0x180027590  mov     r11, rsp
0x180027593  mov     [r11+18h], rbx
0x180027597  mov     [r11+20h], rsi
0x18002759b  push    rdi
0x18002759c  sub     rsp, 20h
0x1800275a0  mov     rdi, rdx
0x1800275a3  mov     rbx, rcx
0x1800275a6  lea     rsi, [rcx-70h]
0x1800275aa  mov     [r11+10h], rsi
0x1800275ae  test    rdx, rdx
0x1800275b1  jz      loc_180027945
0x1800275b7  mov     edx, [rdx]
0x1800275b9  mov     eax, cs:dword_18006E1D8
0x1800275bf  test    eax, eax
0x1800275c1  jz      short loc_1800275EA
0x1800275c3  add     rcx, 138h
0x1800275ca  mov     qword ptr [r11+8], 0
0x1800275d2  mov     dword ptr [rsp+28h+arg_0], edx
0x1800275d6  mov     rax, [rcx]
0x1800275d9  lea     r8, [r11+8]
0x1800275dd  mov     edx, 4
0x1800275e2  mov     rax, [rax]
0x1800275e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275ea  cmp     dword ptr [rdi], 0
0x1800275ed  jnz     loc_1800276BB
0x1800275f3  test    byte ptr [rbx+115h], 1
0x1800275fa  jz      loc_180027924
0x180027600  mov     rax, [rdi+30h]
0x180027604  mov     [rbx+198h], rax
0x18002760b  mov     eax, [rdi+20h]
0x18002760e  test    eax, eax
0x180027610  jnz     short loc_180027641
0x180027612  cmp     cs:byte_18006E80D, 1
0x180027619  jb      loc_180027945
0x18002761f  lea     edx, [rax+60h]
0x180027622  lea     r8, WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids
0x180027629  mov     rcx, cs:WPP_GLOBAL_Control
0x180027630  mov     rcx, [rcx+0D8h]
0x180027637  call    WPP_SF_
0x18002763c  jmp     loc_180027945
0x180027641  mov     [rbx+188h], eax
0x180027647  mov     eax, [rdi+24h]
0x18002764a  mov     [rbx+18Ch], eax
0x180027650  mov     eax, [rdi+28h]
0x180027653  mov     [rbx+190h], eax
0x180027659  lea     rdx, [rbx+178h]
0x180027660  mov     eax, [rdi+10h]
0x180027663  mov     [rdx], eax
0x180027665  mov     eax, [rdi+14h]
0x180027668  mov     [rbx+17Ch], eax
0x18002766e  mov     eax, [rdi+18h]
0x180027671  mov     [rbx+180h], eax
0x180027677  mov     eax, [rdi+1Ch]
0x18002767a  mov     [rbx+184h], eax
0x180027680  or      byte ptr [rbx+116h], 1
0x180027687  mov     eax, cs:dword_18006E1D8
0x18002768d  test    eax, eax
0x18002768f  jz      loc_180027924
0x180027695  lea     rcx, [rbx+138h]
0x18002769c  mov     [rsp+28h+arg_0], rdx
0x1800276a1  mov     rax, [rcx]
0x1800276a4  lea     r8, [rsp+28h+arg_0]
0x1800276a9  mov     edx, 2
0x1800276ae  mov     rax, [rax]
0x1800276b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800276b6  jmp     loc_180027924
0x1800276bb  cmp     dword ptr [rdi], 3
0x1800276be  jnz     loc_18002784C
0x1800276c4  test    byte ptr [rbx+115h], 2
0x1800276cb  jz      loc_180027924
0x1800276d1  mov     rcx, rsi; this
0x1800276d4  call    ?CleanupSeekTable@CFLACSource@@AEAAXXZ; CFLACSource::CleanupSeekTable(void)
0x1800276d9  mov     eax, [rdi+10h]
0x1800276dc  mov     [rbx+1D0h], eax
0x1800276e2  mov     r8d, [rdi+10h]
0x1800276e6  mov     eax, cs:dword_18006E1D8
0x1800276ec  test    eax, eax
0x1800276ee  jz      short loc_18002771A
0x1800276f0  lea     rcx, [rbx+138h]
0x1800276f7  mov     [rsp+28h+arg_0], 0
0x180027700  mov     dword ptr [rsp+28h+arg_0], r8d
0x180027705  mov     rax, [rcx]
0x180027708  lea     r8, [rsp+28h+arg_0]
0x18002770d  mov     edx, 3
0x180027712  mov     rax, [rax]
0x180027715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002771a  mov     eax, [rbx+1D0h]
0x180027720  test    eax, eax
0x180027722  jz      loc_180027945
0x180027728  mov     ecx, eax
0x18002772a  mov     eax, 18h
0x18002772f  mul     rcx
0x180027732  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180027739  cmovb   rax, rsi
0x18002773d  mov     rcx, rax; unsigned __int64
0x180027740  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180027745  mov     rcx, rax; Destination
0x180027748  mov     [rbx+1D8h], rax
0x18002774f  test    rax, rax
0x180027752  jnz     short loc_180027769
0x180027754  cmp     cs:byte_18006E80D, 1
0x18002775b  jb      loc_180027945
0x180027761  lea     edx, [rsi+62h]
0x180027764  jmp     loc_180027622
0x180027769  mov     eax, [rbx+1D0h]
0x18002776f  lea     rdx, [rax+rax*2]
0x180027773  shl     rdx, 3; DestinationSize
0x180027777  mov     r9, rdx; SourceSize
0x18002777a  mov     r8, [rdi+18h]; Source
0x18002777e  call    memcpy_s
0x180027783  test    eax, eax
0x180027785  jz      short loc_18002779E
0x180027787  cmp     cs:byte_18006E80D, 1
0x18002778e  jb      loc_180027945
0x180027794  mov     edx, 62h ; 'b'
0x180027799  jmp     loc_180027622
0x18002779e  mov     ecx, [rbx+1D0h]
0x1800277a4  mov     eax, 8
0x1800277a9  mul     rcx
0x1800277ac  cmovb   rax, rsi
0x1800277b0  mov     rcx, rax; unsigned __int64
0x1800277b3  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800277b8  mov     [rbx+108h], rax
0x1800277bf  test    rax, rax
0x1800277c2  jnz     short loc_1800277D9
0x1800277c4  cmp     cs:byte_18006E80D, 1
0x1800277cb  jb      loc_180027945
0x1800277d1  lea     edx, [rax+63h]
0x1800277d4  jmp     loc_180027622
0x1800277d9  test    byte ptr [rbx+116h], 1
0x1800277e0  jnz     short loc_1800277F9
0x1800277e2  cmp     cs:byte_18006E80D, 1
0x1800277e9  jb      loc_180027945
0x1800277ef  mov     edx, 64h ; 'd'
0x1800277f4  jmp     loc_180027622
0x1800277f9  xor     r10d, r10d
0x1800277fc  cmp     [rbx+1D0h], r10d
0x180027803  jle     short loc_180027840
0x180027805  movsxd  r9, r10d
0x180027808  lea     r8, [r9+r9*2]
0x18002780c  mov     rax, [rbx+1D8h]
0x180027813  mov     ecx, [rbx+188h]
0x180027819  xor     edx, edx
0x18002781b  mov     rax, [rax+r8*8]
0x18002781f  div     rcx
0x180027822  imul    rcx, rax, 989680h
0x180027829  mov     rax, [rbx+108h]
0x180027830  mov     [rax+r9*8], rcx
0x180027834  inc     r10d
0x180027837  cmp     r10d, [rbx+1D0h]
0x18002783e  jl      short loc_180027805
0x180027840  or      byte ptr [rbx+116h], 2
0x180027847  jmp     loc_180027924
0x18002784c  cmp     dword ptr [rdi], 6
0x18002784f  jnz     loc_180027924
0x180027855  test    byte ptr [rsi+185h], 8
0x18002785c  jz      loc_180027924
0x180027862  mov     rcx, rsi; this
0x180027865  call    ?CleanupPictureData@CFLACSource@@AEAAXXZ; CFLACSource::CleanupPictureData(void)
0x18002786a  mov     rcx, [rdi+18h]
0x18002786e  jmp     short loc_180027879
0x180027870  sub     al, 20h ; ' '
0x180027872  cmp     al, 5Eh ; '^'
0x180027874  ja      short loc_1800278BD
0x180027876  inc     rcx
0x180027879  mov     al, [rcx]
0x18002787b  test    al, al
0x18002787d  jnz     short loc_180027870
0x18002787f  mov     eax, [rdi+34h]
0x180027882  mov     [rbx+204h], eax
0x180027888  mov     eax, [rdi+38h]
0x18002788b  mov     [rbx+208h], eax
0x180027891  mov     ecx, eax; cb
0x180027893  call    cs:__imp_CoTaskMemAlloc
0x180027899  mov     rcx, rax; Destination
0x18002789c  mov     [rbx+210h], rax
0x1800278a3  test    rax, rax
0x1800278a6  jnz     short loc_1800278D0
0x1800278a8  cmp     cs:byte_18006E80D, 1
0x1800278af  jb      loc_180027945
0x1800278b5  lea     edx, [rax+66h]
0x1800278b8  jmp     loc_180027622
0x1800278bd  cmp     cs:byte_18006E80D, 1
0x1800278c4  jb      short loc_180027945
0x1800278c6  mov     edx, 65h ; 'e'
0x1800278cb  jmp     loc_180027622
0x1800278d0  mov     eax, [rdi+30h]
0x1800278d3  mov     [rbx+200h], eax
0x1800278d9  mov     eax, [rdi+2Ch]
0x1800278dc  mov     [rbx+1FCh], eax
0x1800278e2  mov     eax, [rdi+28h]
0x1800278e5  mov     [rbx+1F8h], eax
0x1800278eb  mov     eax, [rdi+10h]
0x1800278ee  mov     [rbx+1E0h], eax
0x1800278f4  mov     edx, [rbx+208h]; DestinationSize
0x1800278fa  mov     r9d, edx; SourceSize
0x1800278fd  mov     r8, [rdi+40h]; Source
0x180027901  call    memcpy_s
0x180027906  test    eax, eax
0x180027908  jz      short loc_18002791D
0x18002790a  cmp     cs:byte_18006E80D, 1
0x180027911  jb      short loc_180027945
0x180027913  mov     edx, 67h ; 'g'
0x180027918  jmp     loc_180027622
0x18002791d  or      byte ptr [rbx+116h], 8
0x180027924  mov     eax, [rdi+8]
0x180027927  add     [rbx+118h], eax
0x18002792d  cmp     dword ptr [rdi+4], 0
0x180027931  jz      short loc_180027945
0x180027933  mov     rcx, [rbx+120h]; hEvent
0x18002793a  test    rcx, rcx
0x18002793d  jz      short loc_180027945
0x18002793f  call    cs:__imp_SetEvent
0x180027945  lea     rcx, [rbx+138h]; this
0x18002794c  mov     dl, [rbx+116h]; unsigned __int8
0x180027952  call    ?MetadataTypeSet@CFLACSourceTelemetry@@QEAAXE@Z; CFLACSourceTelemetry::MetadataTypeSet(uchar)
0x180027957  nop
0x180027958  mov     rbx, [rsp+28h+arg_10]
0x18002795d  mov     rsi, [rsp+28h+arg_18]
0x180027962  add     rsp, 20h
0x180027966  pop     rdi
0x180027967  retn
```
