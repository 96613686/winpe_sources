# CPDBErrorDefault::SetLastError(long,wchar_t const *)

- ea: `0x180035320`
- end: `0x1800354e4`
- name: `?SetLastError@CPDBErrorDefault@@UEAAXJPEB_W@Z`
- size: `452`
- prototype: `void __fastcall(CPDBErrorDefault *__hidden this, int, const wchar_t *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800269f8`
- `0x180027430`
- `0x180028ea0`
- `0x180035320`
- `0x1800359d0`
- `0x180035af0`
- `0x1800362d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180035455`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800354bf`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180035455`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800354bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180035342`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180035342`

## pseudocode

```c
void __fastcall CPDBErrorDefault::SetLastError(CPDBErrorDefault *this, unsigned int a2, const wchar_t *a3)
{
  __int64 CurrentThreadId; // rsi
  _WORD *v7; // rax
  unsigned int v8; // edx
  _DWORD *v9; // r8
  _BYTE v10[2048]; // [rsp+20h] [rbp-808h] BYREF
  unsigned int v11; // [rsp+838h] [rbp+10h] BYREF

  *((_DWORD *)this + 2) = a2;
  CurrentThreadId = GetCurrentThreadId();
  if ( !(unsigned int)pdb_internal::Map<unsigned long,long,pdb_internal::HashClass<unsigned long,6>,void,CriticalSectionNoLog>::add(
                        (char *)this + 32,
                        CurrentThreadId,
                        a2) )
    *((_BYTE *)this + 24) = 1;
  v7 = (_WORD *)*((_QWORD *)this + 2);
  if ( a3 )
  {
    if ( v7
      || (v7 = operator new[](0x800u, (const struct std::nothrow_t *)&std::nothrow), (*((_QWORD *)this + 2) = v7) != 0) )
    {
      _o_wcsncpy_s(v7, 1024, a3, -1);
    }
    memset_0(v10, 0, sizeof(v10));
    if ( (unsigned int)pdb_internal::Map<unsigned long,std::array<wchar_t,1024>,pdb_internal::HashClass<unsigned long,6>,void,CriticalSectionNoLog>::add2(
                         (char *)this + 144,
                         (unsigned int)CurrentThreadId,
                         v10)
      && (unsigned int)pdb_internal::Map<unsigned long,char *,pdb_internal::HashClass<unsigned long,6>,void,CriticalSectionNop>::find(
                         (char *)this + 144,
                         (unsigned int)CurrentThreadId,
                         &v11) )
    {
      _o_wcsncpy_s(*((_QWORD *)this + 22) + ((unsigned __int64)v11 << 11), 1024, a3, -1);
    }
    else
    {
      *((_BYTE *)this + 24) = 1;
    }
  }
  else
  {
    if ( v7 )
      *v7 = 0;
    if ( (unsigned int)pdb_internal::Map<unsigned long,char *,pdb_internal::HashClass<unsigned long,6>,void,CriticalSectionNop>::find(
                         (char *)this + 144,
                         (unsigned int)CurrentThreadId,
                         &v11)
      && (unsigned int)pdb_internal::Map<unsigned long,char *,pdb_internal::HashClass<unsigned long,6>,void,CriticalSectionNop>::find(
                         (char *)this + 144,
                         (unsigned int)CurrentThreadId,
                         &v11) )
    {
      v8 = v11;
      if ( v11 < 32 * *((_DWORD *)this + 52) )
      {
        v9 = (_DWORD *)(*((_QWORD *)this + 25) + 4 * ((unsigned __int64)v11 >> 5));
        *v9 &= ~(1 << v11);
      }
      if ( (unsigned int)pdb_internal::ISet::add((CPDBErrorDefault *)((char *)this + 216), v8) )
      {
        --*((_DWORD *)this + 60);
      }
      else if ( (unsigned int)pdb_internal::Map<unsigned long,char *,pdb_internal::HashClass<unsigned long,6>,void,CriticalSectionNop>::find(
                                (char *)this + 144,
                                (unsigned int)CurrentThreadId,
                                &v11) )
      {
        *(_WORD *)(((unsigned __int64)v11 << 11) + *((_QWORD *)this + 22)) = 0;
      }
    }
  }
}

```

## disassembly

```asm
0x180035320  mov     [rsp+arg_0], rbx
0x180035325  mov     [rsp+arg_10], rbp
0x18003532a  mov     [rsp+arg_18], rsi
0x18003532f  push    rdi
0x180035330  sub     rsp, 820h
0x180035337  mov     rbp, r8
0x18003533a  mov     [rcx+8], edx
0x18003533d  mov     ebx, edx
0x18003533f  mov     rdi, rcx
0x180035342  call    cs:__imp_GetCurrentThreadId
0x180035348  lea     rcx, [rdi+20h]
0x18003534c  mov     r8d, ebx
0x18003534f  mov     edx, eax
0x180035351  mov     esi, eax
0x180035353  call    ?add@?$Map@KJV?$HashClass@K$05@pdb_internal@@XVCriticalSectionNoLog@@@pdb_internal@@QEAAHKJ@Z; pdb_internal::Map<ulong,long,pdb_internal::HashClass<ulong,6>,void,CriticalSectionNoLog>::add(ulong,long)
0x180035358  test    eax, eax
0x18003535a  jnz     short loc_180035360
0x18003535c  mov     byte ptr [rdi+18h], 1
0x180035360  mov     rax, [rdi+10h]
0x180035364  test    rbp, rbp
0x180035367  jnz     loc_180035424
0x18003536d  test    rax, rax
0x180035370  jz      short loc_180035375
0x180035372  mov     [rax], bp
0x180035375  lea     rbx, [rdi+90h]
0x18003537c  mov     edx, esi
0x18003537e  mov     rcx, rbx
0x180035381  lea     r8, [rsp+828h+arg_8]
0x180035389  call    ?find@?$Map@KPEADV?$HashClass@K$05@pdb_internal@@XVCriticalSectionNop@@@pdb_internal@@IEBAHKPEAI@Z; pdb_internal::Map<ulong,char *,pdb_internal::HashClass<ulong,6>,void,CriticalSectionNop>::find(ulong,uint *)
0x18003538e  test    eax, eax
0x180035390  jz      loc_1800354CB
0x180035396  lea     r8, [rsp+828h+arg_8]
0x18003539e  mov     edx, esi
0x1800353a0  mov     rcx, rbx
0x1800353a3  call    ?find@?$Map@KPEADV?$HashClass@K$05@pdb_internal@@XVCriticalSectionNop@@@pdb_internal@@IEBAHKPEAI@Z; pdb_internal::Map<ulong,char *,pdb_internal::HashClass<ulong,6>,void,CriticalSectionNop>::find(ulong,uint *)
0x1800353a8  test    eax, eax
0x1800353aa  jz      loc_1800354CB
0x1800353b0  mov     eax, [rbx+40h]
0x1800353b3  mov     edx, [rsp+828h+arg_8]; unsigned int
0x1800353ba  shl     eax, 5
0x1800353bd  cmp     edx, eax
0x1800353bf  jnb     short loc_1800353DD
0x1800353c1  mov     rax, [rbx+38h]
0x1800353c5  mov     ecx, edx
0x1800353c7  shr     rcx, 5
0x1800353cb  lea     r8, [rax+rcx*4]
0x1800353cf  mov     ecx, edx
0x1800353d1  mov     eax, 1
0x1800353d6  shl     eax, cl
0x1800353d8  not     eax
0x1800353da  and     [r8], eax
0x1800353dd  lea     rcx, [rbx+48h]; this
0x1800353e1  call    ?add@ISet@pdb_internal@@QEAAHI@Z; pdb_internal::ISet::add(uint)
0x1800353e6  test    eax, eax
0x1800353e8  jz      short loc_1800353F2
0x1800353ea  dec     dword ptr [rbx+60h]
0x1800353ed  jmp     loc_1800354CB
0x1800353f2  lea     r8, [rsp+828h+arg_8]
0x1800353fa  mov     edx, esi
0x1800353fc  mov     rcx, rbx
0x1800353ff  call    ?find@?$Map@KPEADV?$HashClass@K$05@pdb_internal@@XVCriticalSectionNop@@@pdb_internal@@IEBAHKPEAI@Z; pdb_internal::Map<ulong,char *,pdb_internal::HashClass<ulong,6>,void,CriticalSectionNop>::find(ulong,uint *)
0x180035404  test    eax, eax
0x180035406  jz      loc_1800354CB
0x18003540c  mov     ecx, [rsp+828h+arg_8]
0x180035413  mov     rax, [rbx+20h]
0x180035417  shl     rcx, 0Bh
0x18003541b  mov     [rcx+rax], bp
0x18003541f  jmp     loc_1800354CB
0x180035424  test    rax, rax
0x180035427  jnz     short loc_180035443
0x180035429  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180035430  mov     ecx, 800h; unsigned __int64
0x180035435  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003543a  mov     [rdi+10h], rax
0x18003543e  test    rax, rax
0x180035441  jz      short loc_18003545B
0x180035443  mov     r9, 0FFFFFFFFFFFFFFFFh
0x18003544a  mov     r8, rbp
0x18003544d  mov     edx, 400h
0x180035452  mov     rcx, rax
0x180035455  call    cs:__imp__o_wcsncpy_s
0x18003545b  xor     edx, edx; Val
0x18003545d  lea     rcx, [rsp+828h+var_808]; void *
0x180035462  mov     r8d, 800h; Size
0x180035468  call    memset_0
0x18003546d  lea     r8, [rsp+828h+var_808]
0x180035472  mov     edx, esi
0x180035474  lea     rcx, [rdi+90h]
0x18003547b  call    ?add2@?$Map@KV?$array@_W$0EAA@@std@@V?$HashClass@K$05@pdb_internal@@XVCriticalSectionNoLog@@@pdb_internal@@QEAAHKAEBV?$array@_W$0EAA@@std@@@Z; pdb_internal::Map<ulong,std::array<wchar_t,1024>,pdb_internal::HashClass<ulong,6>,void,CriticalSectionNoLog>::add2(ulong,std::array<wchar_t,1024> const &)
0x180035480  test    eax, eax
0x180035482  jz      short loc_1800354C7
0x180035484  lea     r8, [rsp+828h+arg_8]
0x18003548c  mov     edx, esi
0x18003548e  lea     rcx, [rdi+90h]
0x180035495  call    ?find@?$Map@KPEADV?$HashClass@K$05@pdb_internal@@XVCriticalSectionNop@@@pdb_internal@@IEBAHKPEAI@Z; pdb_internal::Map<ulong,char *,pdb_internal::HashClass<ulong,6>,void,CriticalSectionNop>::find(ulong,uint *)
0x18003549a  test    eax, eax
0x18003549c  jz      short loc_1800354C7
0x18003549e  mov     ecx, [rsp+828h+arg_8]
0x1800354a5  mov     r9, 0FFFFFFFFFFFFFFFFh
0x1800354ac  shl     rcx, 0Bh
0x1800354b0  mov     r8, rbp
0x1800354b3  add     rcx, [rdi+0B0h]
0x1800354ba  mov     edx, 400h
0x1800354bf  call    cs:__imp__o_wcsncpy_s
0x1800354c5  jmp     short loc_1800354CB
0x1800354c7  mov     byte ptr [rdi+18h], 1
0x1800354cb  lea     r11, [rsp+828h+var_8]
0x1800354d3  mov     rbx, [r11+10h]
0x1800354d7  mov     rbp, [r11+20h]
0x1800354db  mov     rsi, [r11+28h]
0x1800354df  mov     rsp, r11
0x1800354e2  pop     rdi
0x1800354e3  retn
```
