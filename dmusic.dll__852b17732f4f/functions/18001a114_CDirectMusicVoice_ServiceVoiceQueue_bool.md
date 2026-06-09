# CDirectMusicVoice::ServiceVoiceQueue(bool *)

- ea: `0x18001a114`
- end: `0x18001a2f4`
- name: `?ServiceVoiceQueue@CDirectMusicVoice@@CAXPEA_N@Z`
- size: `480`
- prototype: `void __fastcall(bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18001a6d0`

## callees

- `0x180018fdc`
- `0x180019120`
- `0x180019bc8`
- `0x18001a0d0`
- `0x18001a114`
- `0x18001a480`
- `0x180022010`

## pseudocode

```c
void __fastcall CDirectMusicVoice::ServiceVoiceQueue(bool *a1)
{
  CVSTClient *v1; // rbx
  __int64 v3; // rdi
  bool v4; // zf
  int v5; // ebp
  char v6; // r14
  __int64 v7; // rsi
  CDirectSoundWaveDownload *v8; // rcx
  unsigned __int64 v9; // rdx
  int refreshed; // eax
  unsigned __int64 v11; // rax
  __int64 v12; // rdx
  _QWORD *v13; // rcx
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // r8
  __int64 v16; // rsi
  _QWORD *v17; // rax
  __int64 v18; // r8
  _QWORD *v19; // r10
  __int64 v20; // r9
  __int64 v21; // [rsp+78h] [rbp+10h] BYREF

  v1 = (CVSTClient *)CDirectMusicVoice::m_ClientList;
  v3 = 0;
  while ( v1 )
  {
    v4 = *((_QWORD *)v1 + 3) == 0;
    v21 = 0;
    if ( v4 )
      goto LABEL_35;
    v5 = (***((__int64 (__fastcall ****)(__int64, GUID *, __int64 *))v1 + 1))(
           *((_QWORD *)v1 + 1),
           &IID_IDirectMusicPortPrivate,
           &v21);
    if ( v5 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v21 + 48LL))(
             v21,
             *((_QWORD *)v1 + 3),
             *((unsigned int *)v1 + 10),
             *((_QWORD *)v1 + 4));
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      if ( v5 < 0 )
        goto LABEL_35;
      v3 = *((_QWORD *)v1 + 4);
    }
    if ( v5 >= 0 )
    {
      v6 = 0;
      v7 = (*((_QWORD *)v1 + 2) - 8LL) & -(__int64)(*((_QWORD *)v1 + 2) != 0);
      if ( v7 )
      {
        while ( 1 )
        {
          if ( *(_DWORD *)v3 )
          {
            v8 = *(CDirectSoundWaveDownload **)(v7 + 112);
            v9 = *(_QWORD *)(v3 + 8);
            if ( *((_QWORD *)v8 + 14) )
              refreshed = CDirectSoundWaveDownload::RefreshThroughSampleLooped(v8, v9);
            else
              refreshed = CDirectSoundWaveDownload::RefreshThroughSampleOneShot(v8, v9);
            v5 = refreshed;
            if ( refreshed < 0 )
              goto LABEL_18;
            *(_BYTE *)(v7 + 125) = 1;
          }
          if ( v5 == 1 || !*(_DWORD *)v3 && *(_BYTE *)(v7 + 125) )
          {
            CDirectMusicVoice::Stop((CDirectMusicVoice *)v7, 0);
            *(_BYTE *)(v7 + 124) = 0;
            v6 = 1;
          }
LABEL_18:
          v3 += 16;
          v7 = (*(_QWORD *)(v7 + 8) - 8LL) & -(__int64)(*(_QWORD *)(v7 + 8) != 0);
          if ( !v7 )
          {
            if ( v6 )
            {
              v11 = *((_QWORD *)v1 + 2);
              *a1 = 1;
              v12 = (v11 - 8) & ((unsigned __int128)-(__int128)v11 >> 64);
              while ( v12 )
              {
                v13 = (_QWORD *)(v12 + 8);
                v14 = *(_QWORD *)(v12 + 8);
                v15 = v14 - 8;
                if ( *(_BYTE *)(v12 + 124) )
                {
                  v12 = v15 & ((unsigned __int128)-(__int128)v14 >> 64);
                }
                else
                {
                  v16 = v15 & -(__int64)(v14 != 0);
                  if ( v12 != -8 )
                  {
                    v17 = (_QWORD *)*((_QWORD *)v1 + 2);
                    if ( v13 == v17 )
                    {
                      v18 = *v17;
                      *v17 = 0;
                    }
                    else
                    {
                      v19 = 0;
                      v18 = *((_QWORD *)v1 + 2);
                      if ( v17 )
                      {
                        while ( 1 )
                        {
                          v20 = *v17;
                          if ( v17 == v13 )
                            break;
                          v19 = v17;
                          v17 = (_QWORD *)*v17;
                          if ( !v20 )
                            goto LABEL_31;
                        }
                        *v19 = v20;
                        *v17 = 0;
                        *v13 = 0;
                      }
                    }
LABEL_31:
                    *((_QWORD *)v1 + 2) = v18;
                  }
                  CDirectMusicVoice::Release((CDirectMusicVoice *)v12);
                  v12 = v16;
                }
              }
              CVSTClient::BuildVoiceIdList(v1);
            }
            break;
          }
        }
      }
    }
LABEL_35:
    v1 = *(CVSTClient **)v1;
  }
}

```

## disassembly

```asm
0x18001a114  push    rbx
0x18001a116  push    rbp
0x18001a117  push    rsi
0x18001a118  push    rdi
0x18001a119  push    r14
0x18001a11b  push    r15
0x18001a11d  sub     rsp, 38h
0x18001a121  mov     rbx, cs:?m_ClientList@CDirectMusicVoice@@0VCVSTClientList@@A; CVSTClientList CDirectMusicVoice::m_ClientList
0x18001a128  mov     r15, rcx
0x18001a12b  xor     edi, edi
0x18001a12d  jmp     loc_18001A2DE
0x18001a132  cmp     qword ptr [rbx+18h], 0
0x18001a137  mov     [rsp+68h+arg_8], 0
0x18001a140  jz      loc_18001A2DB
0x18001a146  mov     rcx, [rbx+8]
0x18001a14a  lea     r8, [rsp+68h+arg_8]
0x18001a14f  lea     rdx, IID_IDirectMusicPortPrivate
0x18001a156  mov     rax, [rcx]
0x18001a159  mov     rax, [rax]
0x18001a15c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a161  mov     ebp, eax
0x18001a163  test    eax, eax
0x18001a165  js      short loc_18001A1A3
0x18001a167  mov     rcx, [rsp+68h+arg_8]
0x18001a16c  mov     r9, [rbx+20h]
0x18001a170  mov     r8d, [rbx+28h]
0x18001a174  mov     rdx, [rbx+18h]
0x18001a178  mov     rax, [rcx]
0x18001a17b  mov     rax, [rax+30h]
0x18001a17f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a184  mov     rcx, [rsp+68h+arg_8]
0x18001a189  mov     ebp, eax
0x18001a18b  mov     rax, [rcx]
0x18001a18e  mov     rax, [rax+10h]
0x18001a192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a197  test    ebp, ebp
0x18001a199  js      loc_18001A2DB
0x18001a19f  mov     rdi, [rbx+20h]
0x18001a1a3  test    ebp, ebp
0x18001a1a5  js      loc_18001A2DB
0x18001a1ab  mov     rax, [rbx+10h]
0x18001a1af  xor     r14b, r14b
0x18001a1b2  lea     rcx, [rax-8]
0x18001a1b6  neg     rax
0x18001a1b9  sbb     rsi, rsi
0x18001a1bc  and     rsi, rcx
0x18001a1bf  jz      loc_18001A2DB
0x18001a1c5  cmp     dword ptr [rdi], 0
0x18001a1c8  jz      short loc_18001A1EF
0x18001a1ca  mov     rcx, [rsi+70h]; this
0x18001a1ce  mov     rdx, [rdi+8]; unsigned __int64
0x18001a1d2  cmp     qword ptr [rcx+70h], 0
0x18001a1d7  jnz     short loc_18001A1E0
0x18001a1d9  call    ?RefreshThroughSampleOneShot@CDirectSoundWaveDownload@@QEAAJ_K@Z; CDirectSoundWaveDownload::RefreshThroughSampleOneShot(unsigned __int64)
0x18001a1de  jmp     short loc_18001A1E5
0x18001a1e0  call    ?RefreshThroughSampleLooped@CDirectSoundWaveDownload@@QEAAJ_K@Z; CDirectSoundWaveDownload::RefreshThroughSampleLooped(unsigned __int64)
0x18001a1e5  mov     ebp, eax
0x18001a1e7  test    eax, eax
0x18001a1e9  js      short loc_18001A210
0x18001a1eb  mov     byte ptr [rsi+7Dh], 1
0x18001a1ef  cmp     ebp, 1
0x18001a1f2  jz      short loc_18001A1FF
0x18001a1f4  cmp     dword ptr [rdi], 0
0x18001a1f7  jnz     short loc_18001A210
0x18001a1f9  cmp     byte ptr [rsi+7Dh], 0
0x18001a1fd  jz      short loc_18001A210
0x18001a1ff  xor     edx, edx; __int64
0x18001a201  mov     rcx, rsi; this
0x18001a204  call    ?Stop@CDirectMusicVoice@@UEAAJ_J@Z; CDirectMusicVoice::Stop(__int64)
0x18001a209  mov     byte ptr [rsi+7Ch], 0
0x18001a20d  mov     r14b, 1
0x18001a210  mov     rax, [rsi+8]
0x18001a214  lea     rcx, [rax-8]
0x18001a218  neg     rax
0x18001a21b  sbb     rsi, rsi
0x18001a21e  add     rdi, 10h
0x18001a222  and     rsi, rcx
0x18001a225  jnz     short loc_18001A1C5
0x18001a227  test    r14b, r14b
0x18001a22a  jz      loc_18001A2DB
0x18001a230  mov     rax, [rbx+10h]
0x18001a234  mov     byte ptr [r15], 1
0x18001a238  lea     rcx, [rax-8]
0x18001a23c  neg     rax
0x18001a23f  sbb     rdx, rdx
0x18001a242  and     rdx, rcx
0x18001a245  jz      loc_18001A2D3
0x18001a24b  cmp     byte ptr [rdx+7Ch], 0
0x18001a24f  lea     rcx, [rdx+8]
0x18001a253  mov     rax, [rcx]
0x18001a256  lea     r8, [rax-8]
0x18001a25a  jz      short loc_18001A267
0x18001a25c  neg     rax
0x18001a25f  sbb     rdx, rdx
0x18001a262  and     rdx, r8
0x18001a265  jmp     short loc_18001A2CA
0x18001a267  neg     rax
0x18001a26a  sbb     rsi, rsi
0x18001a26d  and     rsi, r8
0x18001a270  test    rcx, rcx
0x18001a273  jz      short loc_18001A2BF
0x18001a275  mov     rax, [rbx+10h]
0x18001a279  cmp     rcx, rax
0x18001a27c  jnz     short loc_18001A28A
0x18001a27e  mov     r8, [rax]
0x18001a281  mov     qword ptr [rax], 0
0x18001a288  jmp     short loc_18001A2BB
0x18001a28a  xor     r10d, r10d
0x18001a28d  mov     r8, rax
0x18001a290  test    rax, rax
0x18001a293  jz      short loc_18001A2BB
0x18001a295  mov     r9, [rax]
0x18001a298  cmp     rax, rcx
0x18001a29b  jz      short loc_18001A2AA
0x18001a29d  mov     r10, rax
0x18001a2a0  mov     rax, r9
0x18001a2a3  test    r9, r9
0x18001a2a6  jnz     short loc_18001A295
0x18001a2a8  jmp     short loc_18001A2BB
0x18001a2aa  mov     [r10], r9
0x18001a2ad  mov     qword ptr [rax], 0
0x18001a2b4  mov     qword ptr [rcx], 0
0x18001a2bb  mov     [rbx+10h], r8
0x18001a2bf  mov     rcx, rdx; this
0x18001a2c2  call    ?Release@CDirectMusicVoice@@UEAAKXZ; CDirectMusicVoice::Release(void)
0x18001a2c7  mov     rdx, rsi
0x18001a2ca  test    rdx, rdx
0x18001a2cd  jnz     loc_18001A24B
0x18001a2d3  mov     rcx, rbx; this
0x18001a2d6  call    ?BuildVoiceIdList@CVSTClient@@QEAAJXZ; CVSTClient::BuildVoiceIdList(void)
0x18001a2db  mov     rbx, [rbx]
0x18001a2de  test    rbx, rbx
0x18001a2e1  jnz     loc_18001A132
0x18001a2e7  add     rsp, 38h
0x18001a2eb  pop     r15
0x18001a2ed  pop     r14
0x18001a2ef  pop     rdi
0x18001a2f0  pop     rsi
0x18001a2f1  pop     rbp
0x18001a2f2  pop     rbx
0x18001a2f3  retn
```
