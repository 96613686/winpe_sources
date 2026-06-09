# DusmCache::UpdateCostFromConnection(DusmConnection const &,_DUSM_SOURCE)

- ea: `0x18001d910`
- end: `0x18001d992`
- name: `?UpdateCostFromConnection@DusmCache@@SAXAEBVDusmConnection@@W4_DUSM_SOURCE@@@Z`
- size: `130`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18001b688`
- `0x18001b708`
- `0x18001d524`
- `0x18001faa8`
- `0x18001fe44`

## callees

- `0x18001bfec`
- `0x18001d29c`
- `0x18001d87c`
- `0x18001d910`

## string_xrefs

- `0x18001d980`: `onecoreuap\net\dusm\lib\dusmcache.cpp`
- `0x18001d96e`: `DusmCache::UpdateCostFromConnection::source`

## pseudocode

```c
void __fastcall DusmCache::UpdateCostFromConnection(const struct DusmConnection *a1, unsigned int a2)
{
  int v4; // eax
  const char *v5; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v7; // [rsp+50h] [rbp+18h] BYREF

  if ( a2 - 2 > 1 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x39D,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmcache.cpp",
      (const char *)0x57,
      (unsigned int)"DusmCache::UpdateCostFromConnection::source",
      v5);
  if ( a2 == *((_DWORD *)a1 + 6) )
  {
    LODWORD(v7) = DusmCache::GetCostLevelFromConnection();
    v4 = 4;
    if ( a2 == 2 )
      v4 = 2;
    HIDWORD(v7) = v4;
    DusmCache::SetCostSync(2, a1, a2, &v7, 0);
  }
}

```

## disassembly

```asm
0x18001d910  mov     [rsp+arg_0], rbx
0x18001d915  push    rdi
0x18001d916  sub     rsp, 30h
0x18001d91a  lea     eax, [rdx-2]
0x18001d91d  mov     ebx, edx
0x18001d91f  mov     rdi, rcx
0x18001d922  cmp     eax, 1
0x18001d925  ja      short loc_18001D969
0x18001d927  cmp     edx, [rcx+18h]
0x18001d92a  jnz     short loc_18001D95E
0x18001d92c  call    ?GetCostLevelFromConnection@DusmCache@@SA?AW4_DUSM_CONNECTION_COST@@AEBVDusmConnection@@W4_DUSM_SOURCE@@@Z; DusmCache::GetCostLevelFromConnection(DusmConnection const &,_DUSM_SOURCE)
0x18001d931  mov     [rsp+38h+arg_10], eax
0x18001d935  lea     r9, [rsp+38h+arg_10]
0x18001d93a  mov     eax, 4
0x18001d93f  mov     [rsp+38h+var_18], 0
0x18001d947  mov     r8d, ebx
0x18001d94a  mov     rdx, rdi
0x18001d94d  lea     ecx, [rax-2]
0x18001d950  cmp     ebx, ecx
0x18001d952  cmovz   eax, ecx
0x18001d955  mov     [rsp+38h+arg_14], eax
0x18001d959  call    ?SetCostSync@DusmCache@@AEAAXAEBVDusmConnection@@W4_DUSM_SOURCE@@AEBU_DUSM_CONNECTION_COST_DATA@@H@Z; DusmCache::SetCostSync(DusmConnection const &,_DUSM_SOURCE,_DUSM_CONNECTION_COST_DATA const &,int)
0x18001d95e  mov     rbx, [rsp+38h+arg_0]
0x18001d963  add     rsp, 30h
0x18001d967  pop     rdi
0x18001d968  retn
0x18001d969  mov     rcx, [rsp+38h]; this
0x18001d96e  lea     rax, aDusmcacheUpdat; "DusmCache::UpdateCostFromConnection::so"...
0x18001d975  mov     r9d, 57h ; 'W'; char *
0x18001d97b  mov     qword ptr [rsp+38h+var_18], rax; unsigned int
0x18001d980  lea     r8, aOnecoreuapNetD_3; "onecoreuap\\net\\dusm\\lib\\dusmcache.c"...
0x18001d987  mov     edx, 39Dh; void *
0x18001d98c  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
