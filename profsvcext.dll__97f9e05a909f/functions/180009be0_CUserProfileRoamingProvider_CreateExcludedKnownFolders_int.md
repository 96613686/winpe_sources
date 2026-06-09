# CUserProfileRoamingProvider::CreateExcludedKnownFolders(int)

- ea: `0x180009be0`
- end: `0x180009c62`
- name: `?CreateExcludedKnownFolders@CUserProfileRoamingProvider@@UEAAXH@Z`
- size: `130`
- prototype: `void __fastcall(CUserProfileRoamingProvider *__hidden this, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180009be0`
- `0x180009c68`
- `0x180009cf8`
- `0x18000fca8`
- `0x180020010`

## string_xrefs

- `0x180009c48`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`

## pseudocode

```c
void __fastcall CUserProfileRoamingProvider::CreateExcludedKnownFolders(CUserProfileRoamingProvider *this, int a2)
{
  __int64 v3; // rax
  int v4; // eax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  char v6; // [rsp+40h] [rbp+18h] BYREF

  if ( a2
    && ((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1)) & 4) != 0
    && ((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1)) & 1) == 0
    && ((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1)) & 0x40000) == 0 )
  {
    v3 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v6, this);
    v4 = lambda_7ffc8433c4bbeac35c208205a9225132_::operator()(v3);
    if ( v4 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x6DD,
        (int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
        (const char *)(unsigned int)v4);
  }
}

```

## disassembly

```asm
0x180009be0  test    edx, edx
0x180009be2  jz      short locret_180009C61
0x180009be4  push    rbx; int
0x180009be5  sub     rsp, 20h
0x180009be9  mov     rbx, rcx
0x180009bec  mov     rcx, [rcx+8]
0x180009bf0  mov     rax, [rcx]
0x180009bf3  mov     rax, [rax+10h]
0x180009bf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bfc  test    al, 4
0x180009bfe  jz      short loc_180009C5C
0x180009c00  mov     rcx, [rbx+8]
0x180009c04  mov     rax, [rcx]
0x180009c07  mov     rax, [rax+10h]
0x180009c0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c10  test    al, 1
0x180009c12  jnz     short loc_180009C5C
0x180009c14  mov     rcx, [rbx+8]
0x180009c18  mov     rax, [rcx]
0x180009c1b  mov     rax, [rax+10h]
0x180009c1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c24  bt      eax, 12h
0x180009c28  jb      short loc_180009C5C
0x180009c2a  mov     rdx, rbx
0x180009c2d  lea     rcx, [rsp+28h+arg_10]
0x180009c32  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x180009c37  mov     rcx, rax
0x180009c3a  call    _lambda_7ffc8433c4bbeac35c208205a9225132___operator__
0x180009c3f  test    eax, eax
0x180009c41  jns     short loc_180009C5C
0x180009c43  mov     rcx, [rsp+28h]; this
0x180009c48  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x180009c4f  mov     r9d, eax; char *
0x180009c52  mov     edx, 6DDh; void *
0x180009c57  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180009c5c  add     rsp, 20h
0x180009c60  pop     rbx
0x180009c61  retn
```
