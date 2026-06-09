# RasAuthAttributeDestroy

- ea: `0x18001acd8`
- end: `0x18001ae68`
- name: `RasAuthAttributeDestroy`
- size: `400`
- prototype: `HLOCAL __fastcall(_DWORD *hMem)`
- caller_count: `17`
- callee_count: `2`
- tags: ``

## callers

- `0x1800023c0`
- `0x1800031f4`
- `0x180003340`
- `0x18000a9f0`
- `0x18001063c`
- `0x180011778`
- `0x1800125e0`
- `0x180012e38`
- `0x180014210`
- `0x180014880`
- `0x180015d28`
- `0x18001ab0c`
- `0x18001aba0`
- `0x180026d70`
- `0x1800281ac`
- `0x18002a620`
- `0x18002aca4`

## callees

- `0x180001d3e`
- `0x18001acd8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ae2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ae4b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ae2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ae4b`

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
0x18001acd8  test    rcx, rcx
0x18001acdb  jz      locret_18001AE66
0x18001ace1  mov     [rsp+arg_0], rbx
0x18001ace6  mov     [rsp+arg_8], rsi
0x18001aceb  push    rdi
0x18001acec  sub     rsp, 20h
0x18001acf0  xor     esi, esi
0x18001acf2  mov     rbx, rcx
0x18001acf5  cmp     [rcx], esi
0x18001acf7  jz      loc_18001AE48
0x18001acfd  mov     edi, esi
0x18001acff  add     rdi, rdi
0x18001ad02  mov     ecx, [rbx+rdi*8]
0x18001ad05  cmp     ecx, 32h ; '2'
0x18001ad08  jg      loc_18001ADA9
0x18001ad0e  jz      loc_18001AE10
0x18001ad14  cmp     ecx, 19h
0x18001ad17  jg      short loc_18001AD6C
0x18001ad19  jz      loc_18001AE10
0x18001ad1f  sub     ecx, 1
0x18001ad22  jz      loc_18001AE10
0x18001ad28  sub     ecx, 1
0x18001ad2b  jz      loc_18001AE10
0x18001ad31  sub     ecx, 1
0x18001ad34  jz      loc_18001AE10
0x18001ad3a  sub     ecx, 8
0x18001ad3d  jz      loc_18001AE10
0x18001ad43  sub     ecx, 7
0x18001ad46  jz      loc_18001AE10
0x18001ad4c  sub     ecx, 1
0x18001ad4f  jz      loc_18001AE10
0x18001ad55  sub     ecx, 1
0x18001ad58  jz      loc_18001AE10
0x18001ad5e  sub     ecx, 2
0x18001ad61  jz      loc_18001AE10
0x18001ad67  cmp     ecx, 2
0x18001ad6a  jmp     short loc_18001ADDB
0x18001ad6c  sub     ecx, 1Ah
0x18001ad6f  jz      loc_18001AE10
0x18001ad75  sub     ecx, 4
0x18001ad78  jz      loc_18001AE10
0x18001ad7e  sub     ecx, 1
0x18001ad81  jz      loc_18001AE10
0x18001ad87  sub     ecx, 1
0x18001ad8a  jz      loc_18001AE10
0x18001ad90  sub     ecx, 1
0x18001ad93  jz      short loc_18001AE10
0x18001ad95  sub     ecx, 1
0x18001ad98  jz      short loc_18001AE10
0x18001ad9a  sub     ecx, 1
0x18001ad9d  jz      short loc_18001AE10
0x18001ad9f  sub     ecx, 1
0x18001ada2  jz      short loc_18001AE10
0x18001ada4  cmp     ecx, 8
0x18001ada7  jmp     short loc_18001ADDB
0x18001ada9  cmp     ecx, 61h ; 'a'
0x18001adac  jg      short loc_18001ADDF
0x18001adae  jz      short loc_18001AE10
0x18001adb0  sub     ecx, 3Ch ; '<'
0x18001adb3  jz      short loc_18001AE10
0x18001adb5  sub     ecx, 3
0x18001adb8  jz      short loc_18001AE10
0x18001adba  sub     ecx, 3
0x18001adbd  jz      short loc_18001AE10
0x18001adbf  sub     ecx, 1
0x18001adc2  jz      short loc_18001AE10
0x18001adc4  sub     ecx, 0Ah
0x18001adc7  jz      short loc_18001AE10
0x18001adc9  sub     ecx, 1
0x18001adcc  jz      short loc_18001AE10
0x18001adce  sub     ecx, 1
0x18001add1  jz      short loc_18001AE10
0x18001add3  sub     ecx, 1
0x18001add6  jz      short loc_18001AE10
0x18001add8  cmp     ecx, 10h
0x18001addb  jz      short loc_18001AE10
0x18001addd  jmp     short loc_18001AE37
0x18001addf  sub     ecx, 1FA1h
0x18001ade5  jz      short loc_18001AE10
0x18001ade7  sub     ecx, 5
0x18001adea  jz      short loc_18001AE10
0x18001adec  sub     ecx, 94h
0x18001adf2  jz      short loc_18001AE10
0x18001adf4  sub     ecx, 2EEh
0x18001adfa  jz      short loc_18001AE10
0x18001adfc  sub     ecx, 1
0x18001adff  jz      short loc_18001AE10
0x18001ae01  sub     ecx, 1
0x18001ae04  jz      short loc_18001AE10
0x18001ae06  sub     ecx, 1
0x18001ae09  jz      short loc_18001AE10
0x18001ae0b  cmp     ecx, 1
0x18001ae0e  jnz     short loc_18001AE37
0x18001ae10  mov     rcx, [rbx+rdi*8+8]; void *
0x18001ae15  test    rcx, rcx
0x18001ae18  jz      short loc_18001AE37
0x18001ae1a  mov     r8d, [rbx+rdi*8+4]; Size
0x18001ae1f  xor     edx, edx; Val
0x18001ae21  call    memset_0
0x18001ae26  mov     rcx, [rbx+rdi*8+8]; hMem
0x18001ae2b  call    cs:__imp_LocalFree
0x18001ae32  nop     dword ptr [rax+rax+00h]
0x18001ae37  inc     esi
0x18001ae39  mov     eax, esi
0x18001ae3b  add     rax, rax
0x18001ae3e  cmp     dword ptr [rbx+rax*8], 0
0x18001ae42  jnz     loc_18001ACFD
0x18001ae48  mov     rcx, rbx; hMem
0x18001ae4b  call    cs:__imp_LocalFree
0x18001ae52  nop     dword ptr [rax+rax+00h]
0x18001ae57  mov     rbx, [rsp+28h+arg_0]
0x18001ae5c  mov     rsi, [rsp+28h+arg_8]
0x18001ae61  add     rsp, 20h
0x18001ae65  pop     rdi
0x18001ae66  retn
```
