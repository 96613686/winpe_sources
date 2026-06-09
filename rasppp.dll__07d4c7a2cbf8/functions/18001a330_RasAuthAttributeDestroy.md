# RasAuthAttributeDestroy

- ea: `0x18001a330`
- end: `0x18001a4b3`
- name: `RasAuthAttributeDestroy`
- size: `387`
- prototype: `__int64 __fastcall(HLOCAL hMem)`
- caller_count: `17`
- callee_count: `2`
- tags: ``

## callers

- `0x1800023a8`
- `0x180003190`
- `0x1800032b0`
- `0x18000a610`
- `0x18001016c`
- `0x1800111d8`
- `0x180011fc0`
- `0x180012794`
- `0x180013b50`
- `0x1800141b0`
- `0x1800155b8`
- `0x18001a170`
- `0x18001a200`
- `0x180025fb0`
- `0x180027340`
- `0x1800296c0`
- `0x180029d0c`

## callees

- `0x180001d3e`
- `0x18001a330`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a483`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a49d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a483`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a49d`

## pseudocode

```c
HLOCAL __fastcall RasAuthAttributeDestroy(_DWORD *hMem)
{
  int v1; // esi
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  bool v12; // zf
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx
  int v28; // ecx
  int v29; // ecx
  int v30; // ecx
  int v31; // ecx
  int v32; // ecx
  int v33; // ecx
  int v34; // ecx
  void *v35; // rcx
  HLOCAL result; // rax

  if ( hMem )
  {
    v1 = 0;
    if ( *hMem )
    {
      do
      {
        v3 = hMem[4 * v1];
        if ( v3 > 50 )
        {
          if ( v3 > 97 )
          {
            v29 = v3 - 8097;
            if ( v29 )
            {
              v30 = v29 - 5;
              if ( v30 )
              {
                v31 = v30 - 148;
                if ( v31 )
                {
                  v32 = v31 - 750;
                  if ( v32 )
                  {
                    v33 = v32 - 1;
                    if ( v33 )
                    {
                      v34 = v33 - 1;
                      if ( v34 )
                      {
                        if ( (unsigned int)(v34 - 1) > 1 )
                          goto LABEL_47;
                      }
                    }
                  }
                }
              }
            }
LABEL_45:
            v35 = *(void **)&hMem[4 * v1 + 2];
            if ( v35 )
            {
              memset_0(v35, 0, (unsigned int)hMem[4 * v1 + 1]);
              LocalFree(*(HLOCAL *)&hMem[4 * v1 + 2]);
            }
            goto LABEL_47;
          }
          if ( v3 == 97 )
            goto LABEL_45;
          v21 = v3 - 60;
          if ( !v21 )
            goto LABEL_45;
          v22 = v21 - 3;
          if ( !v22 )
            goto LABEL_45;
          v23 = v22 - 3;
          if ( !v23 )
            goto LABEL_45;
          v24 = v23 - 1;
          if ( !v24 )
            goto LABEL_45;
          v25 = v24 - 10;
          if ( !v25 )
            goto LABEL_45;
          v26 = v25 - 1;
          if ( !v26 )
            goto LABEL_45;
          v27 = v26 - 1;
          if ( !v27 )
            goto LABEL_45;
          v28 = v27 - 1;
          if ( !v28 )
            goto LABEL_45;
          v12 = v28 == 16;
        }
        else
        {
          if ( v3 == 50 )
            goto LABEL_45;
          if ( v3 > 25 )
          {
            v13 = v3 - 26;
            if ( !v13 )
              goto LABEL_45;
            v14 = v13 - 4;
            if ( !v14 )
              goto LABEL_45;
            v15 = v14 - 1;
            if ( !v15 )
              goto LABEL_45;
            v16 = v15 - 1;
            if ( !v16 )
              goto LABEL_45;
            v17 = v16 - 1;
            if ( !v17 )
              goto LABEL_45;
            v18 = v17 - 1;
            if ( !v18 )
              goto LABEL_45;
            v19 = v18 - 1;
            if ( !v19 )
              goto LABEL_45;
            v20 = v19 - 1;
            if ( !v20 )
              goto LABEL_45;
            v12 = v20 == 8;
          }
          else
          {
            if ( v3 == 25 )
              goto LABEL_45;
            v4 = v3 - 1;
            if ( !v4 )
              goto LABEL_45;
            v5 = v4 - 1;
            if ( !v5 )
              goto LABEL_45;
            v6 = v5 - 1;
            if ( !v6 )
              goto LABEL_45;
            v7 = v6 - 8;
            if ( !v7 )
              goto LABEL_45;
            v8 = v7 - 7;
            if ( !v8 )
              goto LABEL_45;
            v9 = v8 - 1;
            if ( !v9 )
              goto LABEL_45;
            v10 = v9 - 1;
            if ( !v10 )
              goto LABEL_45;
            v11 = v10 - 2;
            if ( !v11 )
              goto LABEL_45;
            v12 = v11 == 2;
          }
        }
        if ( v12 )
          goto LABEL_45;
LABEL_47:
        ++v1;
      }
      while ( hMem[4 * v1] );
    }
    return LocalFree(hMem);
  }
  return result;
}

```

## disassembly

```asm
0x18001a330  test    rcx, rcx
0x18001a333  jz      locret_18001A4B2
0x18001a339  mov     [rsp+arg_0], rbx
0x18001a33e  mov     [rsp+arg_8], rsi
0x18001a343  push    rdi
0x18001a344  sub     rsp, 20h
0x18001a348  xor     esi, esi
0x18001a34a  mov     rbx, rcx
0x18001a34d  cmp     [rcx], esi
0x18001a34f  jz      loc_18001A49A
0x18001a355  mov     edi, esi
0x18001a357  add     rdi, rdi
0x18001a35a  mov     ecx, [rbx+rdi*8]
0x18001a35d  cmp     ecx, 32h ; '2'
0x18001a360  jg      loc_18001A401
0x18001a366  jz      loc_18001A468
0x18001a36c  cmp     ecx, 19h
0x18001a36f  jg      short loc_18001A3C4
0x18001a371  jz      loc_18001A468
0x18001a377  sub     ecx, 1
0x18001a37a  jz      loc_18001A468
0x18001a380  sub     ecx, 1
0x18001a383  jz      loc_18001A468
0x18001a389  sub     ecx, 1
0x18001a38c  jz      loc_18001A468
0x18001a392  sub     ecx, 8
0x18001a395  jz      loc_18001A468
0x18001a39b  sub     ecx, 7
0x18001a39e  jz      loc_18001A468
0x18001a3a4  sub     ecx, 1
0x18001a3a7  jz      loc_18001A468
0x18001a3ad  sub     ecx, 1
0x18001a3b0  jz      loc_18001A468
0x18001a3b6  sub     ecx, 2
0x18001a3b9  jz      loc_18001A468
0x18001a3bf  cmp     ecx, 2
0x18001a3c2  jmp     short loc_18001A433
0x18001a3c4  sub     ecx, 1Ah
0x18001a3c7  jz      loc_18001A468
0x18001a3cd  sub     ecx, 4
0x18001a3d0  jz      loc_18001A468
0x18001a3d6  sub     ecx, 1
0x18001a3d9  jz      loc_18001A468
0x18001a3df  sub     ecx, 1
0x18001a3e2  jz      loc_18001A468
0x18001a3e8  sub     ecx, 1
0x18001a3eb  jz      short loc_18001A468
0x18001a3ed  sub     ecx, 1
0x18001a3f0  jz      short loc_18001A468
0x18001a3f2  sub     ecx, 1
0x18001a3f5  jz      short loc_18001A468
0x18001a3f7  sub     ecx, 1
0x18001a3fa  jz      short loc_18001A468
0x18001a3fc  cmp     ecx, 8
0x18001a3ff  jmp     short loc_18001A433
0x18001a401  cmp     ecx, 61h ; 'a'
0x18001a404  jg      short loc_18001A437
0x18001a406  jz      short loc_18001A468
0x18001a408  sub     ecx, 3Ch ; '<'
0x18001a40b  jz      short loc_18001A468
0x18001a40d  sub     ecx, 3
0x18001a410  jz      short loc_18001A468
0x18001a412  sub     ecx, 3
0x18001a415  jz      short loc_18001A468
0x18001a417  sub     ecx, 1
0x18001a41a  jz      short loc_18001A468
0x18001a41c  sub     ecx, 0Ah
0x18001a41f  jz      short loc_18001A468
0x18001a421  sub     ecx, 1
0x18001a424  jz      short loc_18001A468
0x18001a426  sub     ecx, 1
0x18001a429  jz      short loc_18001A468
0x18001a42b  sub     ecx, 1
0x18001a42e  jz      short loc_18001A468
0x18001a430  cmp     ecx, 10h
0x18001a433  jz      short loc_18001A468
0x18001a435  jmp     short loc_18001A489
0x18001a437  sub     ecx, 1FA1h
0x18001a43d  jz      short loc_18001A468
0x18001a43f  sub     ecx, 5
0x18001a442  jz      short loc_18001A468
0x18001a444  sub     ecx, 94h
0x18001a44a  jz      short loc_18001A468
0x18001a44c  sub     ecx, 2EEh
0x18001a452  jz      short loc_18001A468
0x18001a454  sub     ecx, 1
0x18001a457  jz      short loc_18001A468
0x18001a459  sub     ecx, 1
0x18001a45c  jz      short loc_18001A468
0x18001a45e  sub     ecx, 1
0x18001a461  jz      short loc_18001A468
0x18001a463  cmp     ecx, 1
0x18001a466  jnz     short loc_18001A489
0x18001a468  mov     rcx, [rbx+rdi*8+8]; void *
0x18001a46d  test    rcx, rcx
0x18001a470  jz      short loc_18001A489
0x18001a472  mov     r8d, [rbx+rdi*8+4]; Size
0x18001a477  xor     edx, edx; Val
0x18001a479  call    memset_0
0x18001a47e  mov     rcx, [rbx+rdi*8+8]; hMem
0x18001a483  call    cs:__imp_LocalFree
0x18001a489  inc     esi
0x18001a48b  mov     eax, esi
0x18001a48d  add     rax, rax
0x18001a490  cmp     dword ptr [rbx+rax*8], 0
0x18001a494  jnz     loc_18001A355
0x18001a49a  mov     rcx, rbx; hMem
0x18001a49d  call    cs:__imp_LocalFree
0x18001a4a3  mov     rbx, [rsp+28h+arg_0]
0x18001a4a8  mov     rsi, [rsp+28h+arg_8]
0x18001a4ad  add     rsp, 20h
0x18001a4b1  pop     rdi
0x18001a4b2  retn
```
