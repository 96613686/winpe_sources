# CPersistStreamInit::WriteRowDefinition(CRowInfo &)

- ea: `0x18001f1bc`
- end: `0x18001f517`
- name: `?WriteRowDefinition@CPersistStreamInit@@AEAAJAEAVCRowInfo@@@Z`
- size: `859`
- prototype: `__int64 __fastcall(CPersistStreamInit *__hidden this, struct CRowInfo *)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x18001f1bc`
- `0x18001fbc8`

## callees

- `0x180003c38`
- `0x180004384`
- `0x18001c0a0`
- `0x18001d054`
- `0x18001d1c8`
- `0x18001d42c`
- `0x18001ed5c`
- `0x18001f1bc`
- `0x18001f7c8`
- `0x18001fe94`
- `0x180020248`

## pseudocode

```c
__int64 __fastcall CPersistStreamInit::WriteRowDefinition(CPersistStreamInit *this, void **a2)
{
  unsigned int v3; // edx
  __int64 result; // rax
  unsigned int v6; // eax
  _BYTE *v7; // rdx
  CPersistStreamInit *v8; // rcx
  bool v9; // r9
  __int64 v10; // r8
  bool v11; // r9
  unsigned __int16 v12; // di
  unsigned int v13; // r14d
  unsigned __int16 v14; // dx
  unsigned int v15; // [rsp+70h] [rbp+38h] BYREF

  v15 = 0;
  v3 = *((_DWORD *)this + 12);
  *((_DWORD *)this + 13) = 0;
  result = CPersistStreamInit::Indent(this, v3);
  if ( (int)result >= 0 )
  {
    result = CPersistStreamInit::WriteTag(this, 0x30u, &v15);
    if ( (int)result >= 0 )
    {
      result = CPersistStreamInit::WriteNamespace(this, 0x3Fu);
      if ( (int)result >= 0 )
      {
        result = CPersistStreamInit::WriteTag(this, 5u, &v15);
        if ( (int)result >= 0 )
        {
          result = CPersistStreamInit::WriteTag(this, 0x2Cu, &v15);
          if ( (int)result >= 0 )
          {
            result = CPersistStreamInit::WriteTag(this, 3u, &v15);
            if ( (int)result >= 0 )
            {
              result = CPersistStreamInit::WriteTag(this, 0x2Bu, &v15);
              if ( (int)result >= 0 )
              {
                result = CPersistStreamInit::WriteTag(this, 0x29u, &v15);
                if ( (int)result >= 0 )
                {
                  v6 = CPersistStreamInit::_len(this, a2[20]);
                  result = CPersistStreamInit::Write(v8, v7, v6, &v15, 0);
                  if ( (int)result >= 0 )
                  {
                    result = CPersistStreamInit::WriteTag(this, 0x29u, &v15);
                    if ( (int)result >= 0 )
                    {
                      result = CPersistStreamInit::WriteAttributeDefinition(
                                 this,
                                 *(void **)(*((_QWORD *)this + 9) + 880LL),
                                 *(unsigned __int16 **)(*((_QWORD *)this + 9) + 896LL),
                                 v9,
                                 0,
                                 0);
                      if ( (int)result >= 0 )
                      {
                        result = CPersistStreamInit::WriteRowsetMetaData(this, (struct CRowInfo *)a2, v10, v11);
                        if ( (int)result >= 0 )
                        {
                          result = CPersistStreamInit::WriteTag(this, 0x31u, &v15);
                          if ( (int)result >= 0 )
                          {
                            result = CPersistStreamInit::WriteTag(this, 0x28u, &v15);
                            if ( (int)result >= 0 )
                            {
                              v12 = 0;
                              ++*((_DWORD *)this + 12);
                              v13 = 0;
                              while ( v12 < *(_WORD *)a2 )
                              {
                                if ( (CMetaData::mdGetFlags((CMetaData *)a2, v12) & 0x2000) != 0
                                  || CMetaData::mdGetType((CMetaData *)a2, v14) == 136 )
                                {
                                  result = CPersistStreamInit::WriteRowDefinition(
                                             this,
                                             (struct CRowInfo *)((char *)a2[17] + 256 * (unsigned __int64)v13));
                                  if ( (int)result < 0 )
                                    return result;
                                  ++v13;
                                }
                                else
                                {
                                  result = CPersistStreamInit::WriteColumnDefinition(this, (struct CRowInfo *)a2, v12);
                                  if ( (int)result < 0 )
                                    return result;
                                }
                                ++v12;
                              }
                              CPersistStreamInit::Indent(this, *((_DWORD *)this + 12));
                              result = CPersistStreamInit::WriteTag(this, 0x30u, &v15);
                              if ( (int)result >= 0 )
                              {
                                result = CPersistStreamInit::WriteNamespace(this, 0x3Fu);
                                if ( (int)result >= 0 )
                                {
                                  result = CPersistStreamInit::WriteTag(this, 0xDu, &v15);
                                  if ( (int)result >= 0 )
                                  {
                                    result = CPersistStreamInit::WriteTag(this, 0x2Cu, &v15);
                                    if ( (int)result >= 0 )
                                    {
                                      result = CPersistStreamInit::WriteTag(this, 4u, &v15);
                                      if ( (int)result >= 0 )
                                      {
                                        result = CPersistStreamInit::WriteTag(this, 0x2Bu, &v15);
                                        if ( (int)result >= 0 )
                                        {
                                          result = CPersistStreamInit::WriteTag(this, 0x29u, &v15);
                                          if ( (int)result >= 0 )
                                          {
                                            result = CPersistStreamInit::WriteNamespace(this, 0x41u);
                                            if ( (int)result >= 0 )
                                            {
                                              result = CPersistStreamInit::WriteTag(this, 0x23u, &v15);
                                              if ( (int)result >= 0 )
                                              {
                                                result = CPersistStreamInit::WriteTag(this, 0x29u, &v15);
                                                if ( (int)result >= 0 )
                                                {
                                                  result = CPersistStreamInit::WriteTag(this, 0x32u, &v15);
                                                  if ( (int)result >= 0 )
                                                  {
                                                    result = CPersistStreamInit::WriteTag(this, 0x28u, &v15);
                                                    if ( (int)result >= 0 )
                                                    {
                                                      CPersistStreamInit::Indent(this, --*((_DWORD *)this + 12));
                                                      result = CPersistStreamInit::WriteTag(this, 0x33u, &v15);
                                                      if ( (int)result >= 0 )
                                                      {
                                                        result = CPersistStreamInit::WriteNamespace(this, 0x3Fu);
                                                        if ( (int)result >= 0 )
                                                        {
                                                          result = CPersistStreamInit::WriteTag(this, 5u, &v15);
                                                          if ( (int)result >= 0 )
                                                          {
                                                            result = CPersistStreamInit::WriteTag(this, 0x31u, &v15);
                                                            if ( (int)result >= 0 )
                                                              return CPersistStreamInit::WriteTag(this, 0x28u, &v15);
                                                          }
                                                        }
                                                      }
                                                    }
                                                  }
                                                }
                                              }
                                            }
                                          }
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
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
0x18001f1bc  push    rbp
0x18001f1be  push    rbx
0x18001f1bf  push    rsi
0x18001f1c0  push    rdi
0x18001f1c1  push    r12
0x18001f1c3  push    r14
0x18001f1c5  mov     rbp, rsp
0x18001f1c8  sub     rsp, 38h
0x18001f1cc  mov     rsi, rdx
0x18001f1cf  mov     [rbp+arg_0], 0
0x18001f1d6  mov     edx, [rcx+30h]; unsigned int
0x18001f1d9  mov     rbx, rcx
0x18001f1dc  mov     dword ptr [rcx+34h], 0
0x18001f1e3  call    ?Indent@CPersistStreamInit@@AEAAJK@Z; CPersistStreamInit::Indent(ulong)
0x18001f1e8  test    eax, eax
0x18001f1ea  js      loc_18001F509
0x18001f1f0  lea     r8, [rbp+arg_0]; unsigned int *
0x18001f1f4  mov     dl, 30h ; '0'; unsigned __int8
0x18001f1f6  mov     rcx, rbx; this
0x18001f1f9  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001f1fe  test    eax, eax
0x18001f200  js      loc_18001F509
0x18001f206  mov     dl, 3Fh ; '?'; unsigned __int8
0x18001f208  mov     rcx, rbx; this
0x18001f20b  call    ?WriteNamespace@CPersistStreamInit@@AEAAJE@Z; CPersistStreamInit::WriteNamespace(uchar)
0x18001f210  test    eax, eax
0x18001f212  js      loc_18001F509
0x18001f218  lea     r8, [rbp+arg_0]; unsigned int *
0x18001f21c  mov     dl, 5; unsigned __int8
0x18001f21e  mov     rcx, rbx; this
0x18001f221  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001f226  test    eax, eax
0x18001f228  js      loc_18001F509
0x18001f22e  lea     r8, [rbp+arg_0]; unsigned int *
0x18001f232  mov     dl, 2Ch ; ','; unsigned __int8
0x18001f234  mov     rcx, rbx; this
0x18001f237  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001f23c  test    eax, eax
0x18001f23e  js      loc_18001F509
0x18001f244  lea     r8, [rbp+arg_0]; unsigned int *
0x18001f248  mov     dl, 3; unsigned __int8
0x18001f24a  mov     rcx, rbx; this
0x18001f24d  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001f252  test    eax, eax
0x18001f254  js      loc_18001F509
0x18001f25a  lea     r8, [rbp+arg_0]; unsigned int *
0x18001f25e  mov     dl, 2Bh ; '+'; unsigned __int8
0x18001f260  mov     rcx, rbx; this
0x18001f263  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001f268  test    eax, eax
0x18001f26a  js      loc_18001F509
0x18001f270  lea     r8, [rbp+arg_0]; unsigned int *
0x18001f274  mov     dl, 29h ; ')'; unsigned __int8
0x18001f276  mov     rcx, rbx; this
0x18001f279  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001f27e  test    eax, eax
0x18001f280  js      loc_18001F509
0x18001f286  mov     rdx, [rsi+0A0h]; void *
0x18001f28d  mov     rcx, rbx; this
0x18001f290  call    ?_len@CPersistStreamInit@@AEBAHPEAX@Z; CPersistStreamInit::_len(void *)
0x18001f295  mov     r8d, eax; Size
0x18001f298  mov     [rsp+38h+var_18], 0; bool
0x18001f29d  lea     r9, [rbp+arg_0]; unsigned int *
0x18001f2a1  call    ?Write@CPersistStreamInit@@AEAAJPEAXKPEAK_N@Z; CPersistStreamInit::Write(void *,ulong,ulong *,bool)
0x18001f2a6  test    eax, eax
0x18001f2a8  js      loc_18001F509
0x18001f2ae  lea     r8, [rbp+arg_0]; unsigned int *
0x18001f2b2  mov     dl, 29h ; ')'; unsigned __int8
0x18001f2b4  mov     rcx, rbx; this
0x18001f2b7  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001f2bc  test    eax, eax
0x18001f2be  js      loc_18001F509
0x18001f2c4  mov     rdx, [rbx+48h]
0x18001f2c8  mov     rcx, rbx; this
0x18001f2cb  mov     [rsp+38h+var_10], 0; bool
0x18001f2d0  mov     [rsp+38h+var_18], 0; char
0x18001f2d5  mov     r8, [rdx+380h]; unsigned __int16 *
0x18001f2dc  mov     rdx, [rdx+370h]; void *
0x18001f2e3  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001f2e8  test    eax, eax
0x18001f2ea  js      loc_18001F509
0x18001f2f0  mov     rdx, rsi; struct CRowInfo *
0x18001f2f3  mov     rcx, rbx; this
0x18001f2f6  call    ?WriteRowsetMetaData@CPersistStreamInit@@AEAAJAEAVCRowInfo@@@Z; CPersistStreamInit::WriteRowsetMetaData(CRowInfo &)
0x18001f2fb  test    eax, eax
0x18001f2fd  js      loc_18001F509
0x18001f303  lea     r8, [rbp+arg_0]; unsigned int *
0x18001f307  mov     dl, 31h ; '1'; unsigned __int8
0x18001f309  mov     rcx, rbx; this
0x18001f30c  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001f311  test    eax, eax
0x18001f313  js      loc_18001F509
0x18001f319  lea     r8, [rbp+arg_0]; unsigned int *
0x18001f31d  mov     dl, 28h ; '('; unsigned __int8
0x18001f31f  mov     rcx, rbx; this
0x18001f322  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001f327  test    eax, eax
0x18001f329  js      loc_18001F509
0x18001f32f  mov     r12d, 1
0x18001f335  xor     edi, edi
0x18001f337  add     [rbx+30h], r12d
0x18001f33b  xor     r14d, r14d
0x18001f33e  cmp     di, [rsi]
0x18001f341  jnb     short loc_18001F3A6
0x18001f343  movzx   edx, di; unsigned __int16
0x18001f346  mov     rcx, rsi; this
0x18001f349  call    ?mdGetFlags@CMetaData@@QEAAKG@Z; CMetaData::mdGetFlags(ushort)
0x18001f34e  bt      eax, 0Dh
0x18001f352  jb      short loc_18001F37F
0x18001f354  mov     rcx, rsi; this
0x18001f357  call    ?mdGetType@CMetaData@@QEAAGG@Z; CMetaData::mdGetType(ushort)
0x18001f35c  mov     ecx, 88h
0x18001f361  cmp     ax, cx
0x18001f364  jz      short loc_18001F37F
0x18001f366  movzx   r8d, di; unsigned __int16
0x18001f36a  mov     rdx, rsi; struct CRowInfo *
0x18001f36d  mov     rcx, rbx; this
0x18001f370  call    ?WriteColumnDefinition@CPersistStreamInit@@AEAAJAEAVCRowInfo@@G@Z; CPersistStreamInit::WriteColumnDefinition(CRowInfo &,ushort)
0x18001f375  test    eax, eax
0x18001f377  js      loc_18001F509
0x18001f37d  jmp     short loc_18001F3A0
0x18001f37f  mov     edx, r14d
0x18001f382  mov     rcx, rbx; this
0x18001f385  shl     rdx, 8
0x18001f389  add     rdx, [rsi+88h]; struct CRowInfo *
0x18001f390  call    ?WriteRowDefinition@CPersistStreamInit@@AEAAJAEAVCRowInfo@@@Z; CPersistStreamInit::WriteRowDefinition(CRowInfo &)
0x18001f395  test    eax, eax
0x18001f397  js      loc_18001F509
0x18001f39d  add     r14d, r12d
0x18001f3a0  add     di, r12w
0x18001f3a4  jmp     short loc_18001F33E
0x18001f3a6  mov     edx, [rbx+30h]; unsigned int
0x18001f3a9  mov     rcx, rbx; this
0x18001f3ac  call    ?Indent@CPersistStreamInit@@AEAAJK@Z; CPersistStreamInit::Indent(ulong)
0x18001f3b1  lea     r8, [rbp+arg_0]; unsigned int *
0x18001f3b5  mov     dl, 30h ; '0'; unsigned __int8
0x18001f3b7  mov     rcx, rbx; this
0x18001f3ba  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001f3bf  test    eax, eax
0x18001f3c1  js      loc_18001F509
0x18001f3c7  mov     dl, 3Fh ; '?'; unsigned __int8
0x18001f3c9  mov     rcx, rbx; this
0x18001f3cc  call    ?WriteNamespace@CPersistStreamInit@@AEAAJE@Z; CPersistStreamInit::WriteNamespace(uchar)
0x18001f3d1  test    eax, eax
0x18001f3d3  js      loc_18001F509
0x18001f3d9  lea     r8, [rbp+arg_0]; unsigned int *
0x18001f3dd  mov     dl, 0Dh; unsigned __int8
0x18001f3df  mov     rcx, rbx; this
0x18001f3e2  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001f3e7  test    eax, eax
0x18001f3e9  js      loc_18001F509
0x18001f3ef  lea     r8, [rbp+arg_0]; unsigned int *
0x18001f3f3  mov     dl, 2Ch ; ','; unsigned __int8
0x18001f3f5  mov     rcx, rbx; this
0x18001f3f8  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001f3fd  test    eax, eax
0x18001f3ff  js      loc_18001F509
0x18001f405  lea     r8, [rbp+arg_0]; unsigned int *
0x18001f409  mov     dl, 4; unsigned __int8
0x18001f40b  mov     rcx, rbx; this
0x18001f40e  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001f413  test    eax, eax
0x18001f415  js      loc_18001F509
0x18001f41b  lea     r8, [rbp+arg_0]; unsigned int *
0x18001f41f  mov     dl, 2Bh ; '+'; unsigned __int8
0x18001f421  mov     rcx, rbx; this
0x18001f424  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001f429  test    eax, eax
0x18001f42b  js      loc_18001F509
0x18001f431  lea     r8, [rbp+arg_0]; unsigned int *
0x18001f435  mov     dl, 29h ; ')'; unsigned __int8
0x18001f437  mov     rcx, rbx; this
0x18001f43a  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001f43f  test    eax, eax
0x18001f441  js      loc_18001F509
0x18001f447  mov     dl, 41h ; 'A'; unsigned __int8
0x18001f449  mov     rcx, rbx; this
0x18001f44c  call    ?WriteNamespace@CPersistStreamInit@@AEAAJE@Z; CPersistStreamInit::WriteNamespace(uchar)
0x18001f451  test    eax, eax
0x18001f453  js      loc_18001F509
0x18001f459  lea     r8, [rbp+arg_0]; unsigned int *
0x18001f45d  mov     dl, 23h ; '#'; unsigned __int8
0x18001f45f  mov     rcx, rbx; this
0x18001f462  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001f467  test    eax, eax
0x18001f469  js      loc_18001F509
0x18001f46f  lea     r8, [rbp+arg_0]; unsigned int *
0x18001f473  mov     dl, 29h ; ')'; unsigned __int8
0x18001f475  mov     rcx, rbx; this
0x18001f478  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001f47d  test    eax, eax
0x18001f47f  js      loc_18001F509
0x18001f485  lea     r8, [rbp+arg_0]; unsigned int *
0x18001f489  mov     dl, 32h ; '2'; unsigned __int8
0x18001f48b  mov     rcx, rbx; this
0x18001f48e  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001f493  test    eax, eax
0x18001f495  js      short loc_18001F509
0x18001f497  lea     r8, [rbp+arg_0]; unsigned int *
0x18001f49b  mov     dl, 28h ; '('; unsigned __int8
0x18001f49d  mov     rcx, rbx; this
0x18001f4a0  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001f4a5  test    eax, eax
0x18001f4a7  js      short loc_18001F509
0x18001f4a9  dec     dword ptr [rbx+30h]
0x18001f4ac  mov     rcx, rbx; this
0x18001f4af  mov     edx, [rbx+30h]; unsigned int
0x18001f4b2  call    ?Indent@CPersistStreamInit@@AEAAJK@Z; CPersistStreamInit::Indent(ulong)
0x18001f4b7  lea     r8, [rbp+arg_0]; unsigned int *
0x18001f4bb  mov     dl, 33h ; '3'; unsigned __int8
0x18001f4bd  mov     rcx, rbx; this
0x18001f4c0  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001f4c5  test    eax, eax
0x18001f4c7  js      short loc_18001F509
0x18001f4c9  mov     dl, 3Fh ; '?'; unsigned __int8
0x18001f4cb  mov     rcx, rbx; this
0x18001f4ce  call    ?WriteNamespace@CPersistStreamInit@@AEAAJE@Z; CPersistStreamInit::WriteNamespace(uchar)
0x18001f4d3  test    eax, eax
0x18001f4d5  js      short loc_18001F509
0x18001f4d7  lea     r8, [rbp+arg_0]; unsigned int *
0x18001f4db  mov     dl, 5; unsigned __int8
0x18001f4dd  mov     rcx, rbx; this
0x18001f4e0  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001f4e5  test    eax, eax
0x18001f4e7  js      short loc_18001F509
0x18001f4e9  lea     r8, [rbp+arg_0]; unsigned int *
0x18001f4ed  mov     dl, 31h ; '1'; unsigned __int8
0x18001f4ef  mov     rcx, rbx; this
0x18001f4f2  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001f4f7  test    eax, eax
0x18001f4f9  js      short loc_18001F509
0x18001f4fb  lea     r8, [rbp+arg_0]; unsigned int *
0x18001f4ff  mov     dl, 28h ; '('; unsigned __int8
0x18001f501  mov     rcx, rbx; this
0x18001f504  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001f509  add     rsp, 38h
0x18001f50d  pop     r14
0x18001f50f  pop     r12
0x18001f511  pop     rdi
0x18001f512  pop     rsi
0x18001f513  pop     rbx
0x18001f514  pop     rbp
0x18001f515  retn
```
