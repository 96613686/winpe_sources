# Smb2CacheFileNotFound

- ea: `0x14001b0c0`
- end: `0x14001b2c3`
- name: `Smb2CacheFileNotFound`
- size: `515`
- prototype: `__int64 __fastcall(_QWORD *, struct _NAME_CACHE_CONTROL_ *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x1400236b0`

## callees

- `0x14000ad90`
- `0x14001b0c0`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001b260`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001b260`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001b1d1`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001b1d1`
- `rdbss!RxNameCacheActivateEntry` at `0x14001b242`
- `rdbss!RxNameCacheActivateEntry` at `0x14001b242`
- `rdbss!RxNameCacheCreateEntryEx` at `0x14001b20d`
- `rdbss!RxNameCacheCreateEntryEx` at `0x14001b20d`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14001b1eb`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14001b1eb`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x14001b16f`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x14001b229`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x14001b16f`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x14001b229`
- `mrxsmb!MRxSmbIsStreamFile` at `0x14001b140`
- `mrxsmb!MRxSmbIsStreamFile` at `0x14001b140`

## pseudocode

```c
__int64 __fastcall Smb2CacheFileNotFound(_QWORD *a1, struct _NAME_CACHE_CONTROL_ *a2, int a3)
{
  __int64 v4; // r10
  __int64 v7; // rbp
  __int64 v8; // r9
  __int64 v9; // rbx
  __int64 result; // rax
  __int64 v11; // rdx
  __int64 v12; // rdi
  __int64 v13; // rdx
  ULONG v14; // r15d
  __int64 v15; // rax
  __int64 Entry; // rbx
  __int64 v17; // r9
  __int64 InstanceConfigurationBlock; // rax
  int v19; // ecx
  __int16 v20; // [rsp+28h] [rbp-40h]
  __int64 v21; // [rsp+70h] [rbp+8h] BYREF

  v4 = a1[7];
  v7 = *(_QWORD *)(a1[9] + 40LL);
  v8 = *(_QWORD *)(v4 + 136);
  v9 = *(_QWORD *)(v7 + 40);
  v21 = 0;
  result = *(unsigned int *)(v8 + 8);
  if ( (result & 1) == 0 )
  {
    result = *(_QWORD *)(v4 + 120);
    v11 = *(_QWORD *)(result + 32);
    if ( (*(_DWORD *)(v11 + 96) & 0x80u) == 0 && !*(_BYTE *)(result + 77) )
    {
      result = *(_QWORD *)(v11 + 32);
      if ( (*(_BYTE *)(result + 764) & 4) != 0 )
      {
        v12 = v4 + 360;
        result = MRxSmbIsStreamFile(v4 + 360, 0);
        if ( !(_BYTE)result )
        {
          result = *(_QWORD *)(v9 + 424);
          if ( (*(_DWORD *)(result + 184) & 0x800000) == 0 )
          {
            result = MRxSmbGetInstanceConfigurationBlock(a1[10]);
            if ( *(_DWORD *)(result + 16) )
            {
              v13 = *(_QWORD *)(v7 + 40);
              v14 = *(_DWORD *)(v9 + 264);
              if ( (*(_DWORD *)(*(_QWORD *)(v13 + 424) + 184LL) & 0x800) != 0
                || (v15 = -1, (*(_BYTE *)(*(_QWORD *)(v13 + 24) + 1314LL) & 4) == 0) )
              {
                v15 = *(_QWORD *)(v9 + 96);
              }
              v21 = v15;
              ExAcquirePushLockExclusiveEx(&Smb2FileNotFoundCacheLock, 0);
              Entry = RxNameCacheFetchEntryEx(a2, v12, &v21, 0);
              if ( Entry || (LOBYTE(v17) = 1, (Entry = RxNameCacheCreateEntryEx(a2, v12, &v21, v17)) != 0) )
              {
                *(_DWORD *)(Entry + 48) = a3;
                InstanceConfigurationBlock = MRxSmbGetInstanceConfigurationBlock(a1[10]);
                RxNameCacheActivateEntry(a2, (PNAME_CACHE)Entry, *(_DWORD *)(InstanceConfigurationBlock + 16), v14);
                if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x200) != 0 )
                {
                  v20 = *(_WORD *)v12 >> 1;
                  McTemplateK0pphzr2q_EtwWriteTransfer(
                    v19,
                    (unsigned int)SmbUpdateFNFCache,
                    (_DWORD)a1 + 412,
                    (_DWORD)a1,
                    a1[7],
                    v20,
                    *(_QWORD *)(v12 + 8));
                }
              }
              return ExReleasePushLockExclusiveEx(&Smb2FileNotFoundCacheLock, 0);
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14001b0c0  push    rbx
0x14001b0c2  push    rbp
0x14001b0c3  push    rsi
0x14001b0c4  push    r12
0x14001b0c6  push    r14
0x14001b0c8  sub     rsp, 40h
0x14001b0cc  mov     rax, [rcx+48h]
0x14001b0d0  mov     r12d, r8d
0x14001b0d3  mov     r10, [rcx+38h]
0x14001b0d7  mov     r14, rdx
0x14001b0da  mov     rsi, rcx
0x14001b0dd  mov     rbp, [rax+28h]
0x14001b0e1  mov     r9, [r10+88h]
0x14001b0e8  mov     rbx, [rbp+28h]
0x14001b0ec  mov     [rsp+68h+arg_0], 0
0x14001b0f5  mov     eax, [r9+8]
0x14001b0f9  test    al, 1
0x14001b0fb  jnz     loc_14001B279
0x14001b101  mov     rax, [r10+78h]
0x14001b105  mov     rdx, [rax+20h]
0x14001b109  mov     ecx, [rdx+60h]
0x14001b10c  test    cl, cl
0x14001b10e  js      loc_14001B279
0x14001b114  cmp     byte ptr [rax+4Dh], 0
0x14001b118  jnz     loc_14001B279
0x14001b11e  mov     rax, [rdx+20h]
0x14001b122  test    byte ptr [rax+2FCh], 4
0x14001b129  jz      loc_14001B279
0x14001b12f  mov     [rsp+68h+arg_8], rdi
0x14001b134  xor     edx, edx
0x14001b136  lea     rdi, [r10+168h]
0x14001b13d  mov     rcx, rdi
0x14001b140  call    cs:__imp_MRxSmbIsStreamFile
0x14001b147  nop     dword ptr [rax+rax+00h]
0x14001b14c  test    al, al
0x14001b14e  jnz     loc_14001B274
0x14001b154  mov     rax, [rbx+1A8h]
0x14001b15b  test    dword ptr [rax+0B8h], 800000h
0x14001b165  jnz     loc_14001B274
0x14001b16b  mov     rcx, [rsi+50h]
0x14001b16f  call    cs:__imp_MRxSmbGetInstanceConfigurationBlock
0x14001b176  nop     dword ptr [rax+rax+00h]
0x14001b17b  cmp     dword ptr [rax+10h], 0
0x14001b17f  jz      loc_14001B274
0x14001b185  mov     rdx, [rbp+28h]
0x14001b189  mov     [rsp+68h+arg_10], r15
0x14001b191  mov     r15d, [rbx+108h]
0x14001b198  mov     rax, [rdx+1A8h]
0x14001b19f  test    dword ptr [rax+0B8h], 800h
0x14001b1a9  jnz     short loc_14001B1BF
0x14001b1ab  mov     rax, [rdx+18h]
0x14001b1af  test    byte ptr [rax+522h], 4
0x14001b1b6  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14001b1bd  jnz     short loc_14001B1C3
0x14001b1bf  mov     rax, [rbx+60h]
0x14001b1c3  xor     edx, edx
0x14001b1c5  mov     [rsp+68h+arg_0], rax
0x14001b1ca  lea     rcx, Smb2FileNotFoundCacheLock
0x14001b1d1  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14001b1d8  nop     dword ptr [rax+rax+00h]
0x14001b1dd  xor     r9d, r9d
0x14001b1e0  lea     r8, [rsp+68h+arg_0]
0x14001b1e5  mov     rdx, rdi
0x14001b1e8  mov     rcx, r14
0x14001b1eb  call    cs:__imp_RxNameCacheFetchEntryEx
0x14001b1f2  nop     dword ptr [rax+rax+00h]
0x14001b1f7  mov     rbx, rax
0x14001b1fa  test    rax, rax
0x14001b1fd  jnz     short loc_14001B221
0x14001b1ff  mov     r9b, 1
0x14001b202  lea     r8, [rsp+68h+arg_0]
0x14001b207  mov     rdx, rdi
0x14001b20a  mov     rcx, r14
0x14001b20d  call    cs:__imp_RxNameCacheCreateEntryEx
0x14001b214  nop     dword ptr [rax+rax+00h]
0x14001b219  mov     rbx, rax
0x14001b21c  test    rax, rax
0x14001b21f  jz      short loc_14001B257
0x14001b221  mov     [rbx+30h], r12d
0x14001b225  mov     rcx, [rsi+50h]
0x14001b229  call    cs:__imp_MRxSmbGetInstanceConfigurationBlock
0x14001b230  nop     dword ptr [rax+rax+00h]
0x14001b235  mov     r9d, r15d; MRxContext
0x14001b238  mov     rdx, rbx; NameCache
0x14001b23b  mov     rcx, r14; NameCacheCtl
0x14001b23e  mov     r8d, [rax+10h]; LifeTime
0x14001b242  call    cs:__imp_RxNameCacheActivateEntry
0x14001b249  nop     dword ptr [rax+rax+00h]
0x14001b24e  test    byte ptr cs:WPP_MAIN_CB.Queue+11h, 2
0x14001b255  jnz     short loc_14001B286
0x14001b257  xor     edx, edx
0x14001b259  lea     rcx, Smb2FileNotFoundCacheLock
0x14001b260  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14001b267  nop     dword ptr [rax+rax+00h]
0x14001b26c  mov     r15, [rsp+68h+arg_10]
0x14001b274  mov     rdi, [rsp+68h+arg_8]
0x14001b279  add     rsp, 40h
0x14001b27d  pop     r14
0x14001b27f  pop     r12
0x14001b281  pop     rsi
0x14001b282  pop     rbp
0x14001b283  pop     rbx
0x14001b284  retn
0x14001b286  movzx   edx, word ptr [rdi]
0x14001b289  lea     r8, [rsi+19Ch]
0x14001b290  mov     rax, [rdi+8]
0x14001b294  mov     r9, rsi
0x14001b297  shr     dx, 1
0x14001b29a  mov     [rsp+68h+var_30], 0
0x14001b2a2  mov     [rsp+68h+var_38], rax
0x14001b2a7  mov     rax, [rsi+38h]
0x14001b2ab  mov     [rsp+68h+var_40], dx
0x14001b2b0  lea     rdx, SmbUpdateFNFCache
0x14001b2b7  mov     [rsp+68h+var_48], rax
0x14001b2bc  call    McTemplateK0pphzr2q_EtwWriteTransfer
0x14001b2c1  jmp     short loc_14001B257
```
