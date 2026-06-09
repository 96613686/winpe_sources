# DusmCache::SetCostFlagForDataPlan(DusmConnection const &)

- ea: `0x18001d1d0`
- end: `0x18001d294`
- name: `?SetCostFlagForDataPlan@DusmCache@@SAXAEBVDusmConnection@@@Z`
- size: `196`
- prototype: `void __fastcall(const struct DusmConnection *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18001efd0`
- `0x18001f708`

## callees

- `0x180019278`
- `0x18001c508`
- `0x18001d1d0`
- `0x18001d29c`
- `0x18001d87c`

## string_xrefs

- `0x18001d282`: `onecoreuap\net\dusm\lib\dusmcache.cpp`
- `0x18001d270`: `DusmCache::SetCostFlagForDataPlan::source`

## pseudocode

```c
void __fastcall DusmCache::SetCostFlagForDataPlan(const struct DusmConnection *a1)
{
  unsigned int v1; // edi
  bool v3; // al
  __int64 v4; // rcx
  int v5; // esi
  bool v6; // bp
  __int64 v7; // rcx
  const char *v8; // [rsp+28h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  __int64 v10; // [rsp+60h] [rbp+8h] BYREF

  v1 = *((_DWORD *)a1 + 6);
  if ( v1 - 2 > 1 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x3B8,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmcache.cpp",
      (const char *)0x57,
      (unsigned int)"DusmCache::SetCostFlagForDataPlan::source",
      v8);
  v3 = DusmConnection::IsNearLimit(a1);
  v5 = *(_DWORD *)(v4 + 12);
  v10 = 0;
  v6 = v3;
  if ( (unsigned int)DusmCache::QueryCostAsync(v4, v4, v1, &v10) )
  {
    v7 = (unsigned int)v10;
    if ( v6 )
    {
      if ( v5 != 1 )
      {
        LODWORD(v7) = v10 & 0xFFF6FFFF | 0x80000;
        goto LABEL_9;
      }
    }
    else if ( v5 != 1 )
    {
      v7 = (unsigned int)v10 & 0xFFF6FFFF;
LABEL_9:
      if ( (_DWORD)v7 != (_DWORD)v10 )
      {
        LODWORD(v10) = v7;
        DusmCache::SetCostSync(v7, a1, v1, &v10, 0);
      }
      return;
    }
    LODWORD(v7) = v10 & 0xFFF6FFFF | 0x10000;
    goto LABEL_9;
  }
}

```

## disassembly

```asm
0x18001d1d0  push    rbx
0x18001d1d2  push    rbp
0x18001d1d3  push    rsi
0x18001d1d4  push    rdi
0x18001d1d5  sub     rsp, 38h
0x18001d1d9  mov     edi, [rcx+18h]
0x18001d1dc  mov     rbx, rcx
0x18001d1df  lea     eax, [rdi-2]
0x18001d1e2  cmp     eax, 1
0x18001d1e5  ja      loc_18001D26B
0x18001d1eb  call    ?IsNearLimit@DusmConnection@@QEBA_NXZ; DusmConnection::IsNearLimit(void)
0x18001d1f0  mov     esi, [rcx+0Ch]
0x18001d1f3  lea     r9, [rsp+58h+arg_0]
0x18001d1f8  mov     r8d, edi
0x18001d1fb  mov     [rsp+58h+arg_0], 0
0x18001d204  mov     rdx, rcx
0x18001d207  mov     bpl, al
0x18001d20a  call    ?QueryCostAsync@DusmCache@@AEAAHAEBVDusmConnection@@W4_DUSM_SOURCE@@PEAU_DUSM_CONNECTION_COST_DATA@@@Z; DusmCache::QueryCostAsync(DusmConnection const &,_DUSM_SOURCE,_DUSM_CONNECTION_COST_DATA *)
0x18001d20f  test    eax, eax
0x18001d211  jz      short loc_18001D262
0x18001d213  mov     ecx, dword ptr [rsp+58h+arg_0]
0x18001d217  mov     edx, ecx
0x18001d219  test    bpl, bpl
0x18001d21c  jz      short loc_18001D22D
0x18001d21e  cmp     esi, 1
0x18001d221  jz      short loc_18001D232
0x18001d223  btr     ecx, 10h
0x18001d227  bts     ecx, 13h
0x18001d22b  jmp     short loc_18001D242
0x18001d22d  cmp     esi, 1
0x18001d230  jnz     short loc_18001D23C
0x18001d232  btr     ecx, 13h
0x18001d236  bts     ecx, 10h
0x18001d23a  jmp     short loc_18001D242
0x18001d23c  and     ecx, 0FFF6FFFFh
0x18001d242  cmp     ecx, edx
0x18001d244  jz      short loc_18001D262
0x18001d246  lea     r9, [rsp+58h+arg_0]
0x18001d24b  mov     dword ptr [rsp+58h+arg_0], ecx
0x18001d24f  mov     r8d, edi
0x18001d252  mov     [rsp+58h+var_38], 0
0x18001d25a  mov     rdx, rbx
0x18001d25d  call    ?SetCostSync@DusmCache@@AEAAXAEBVDusmConnection@@W4_DUSM_SOURCE@@AEBU_DUSM_CONNECTION_COST_DATA@@H@Z; DusmCache::SetCostSync(DusmConnection const &,_DUSM_SOURCE,_DUSM_CONNECTION_COST_DATA const &,int)
0x18001d262  add     rsp, 38h
0x18001d266  pop     rdi
0x18001d267  pop     rsi
0x18001d268  pop     rbp
0x18001d269  pop     rbx
0x18001d26a  retn
0x18001d26b  mov     rcx, [rsp+58h]; this
0x18001d270  lea     rax, aDusmcacheSetco_2; "DusmCache::SetCostFlagForDataPlan::sour"...
0x18001d277  mov     r9d, 57h ; 'W'; char *
0x18001d27d  mov     qword ptr [rsp+58h+var_38], rax; unsigned int
0x18001d282  lea     r8, aOnecoreuapNetD_3; "onecoreuap\\net\\dusm\\lib\\dusmcache.c"...
0x18001d289  mov     edx, 3B8h; void *
0x18001d28e  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
