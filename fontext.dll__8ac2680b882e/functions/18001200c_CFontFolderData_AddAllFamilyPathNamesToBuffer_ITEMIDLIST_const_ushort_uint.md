# CFontFolderData::_AddAllFamilyPathNamesToBuffer(_ITEMIDLIST const *,ushort * *,uint *)

- ea: `0x18001200c`
- end: `0x180012109`
- name: `?_AddAllFamilyPathNamesToBuffer@CFontFolderData@@AEAAJPEFBU_ITEMIDLIST@@PEAPEAGPEAI@Z`
- size: `253`
- prototype: `__int64 __fastcall(CFontFolderData *this, const struct _ITEMIDLIST *, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800123e8`

## callees

- `0x18001200c`
- `0x180012110`
- `0x180012d60`
- `0x1800225ac`
- `0x18003104a`
- `0x180031070`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800120d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800120d3`

## pseudocode

```c
__int64 __fastcall CFontFolderData::_AddAllFamilyPathNamesToBuffer(
        CFontFolderData *this,
        const struct _ITEMIDLIST *a2,
        unsigned __int16 **a3,
        unsigned int *a4)
{
  int v7; // ebx
  CFontFolderData *v8; // rcx
  LPVOID pv; // [rsp+30h] [rbp-78h] BYREF
  void *v11; // [rsp+38h] [rbp-70h] BYREF
  unsigned __int16 v12[32]; // [rsp+40h] [rbp-68h] BYREF

  memset_0(v12, 0, sizeof(v12));
  v7 = FID_FamilyName(a2, v12, 0x20u);
  if ( v7 >= 0 )
  {
    v11 = 0;
    v7 = CFontFolderEnum::CreateInstance(v12, 0x40u, &GUID_000214f2_0000_0000_c000_000000000046, &v11);
    if ( v7 >= 0 )
    {
      pv = 0;
      while ( !(*(unsigned int (__fastcall **)(void *, __int64, LPVOID *))(*(_QWORD *)v11 + 24LL))(v11, 1, &pv)
           && v7 >= 0 )
      {
        v7 = CFontFolderData::_AddPathNamesToBuffer(v8, (const struct _ITEMIDLIST *)pv, a3, a4);
        if ( pv )
          CoTaskMemFree(pv);
      }
      (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001200c  push    rbx
0x18001200e  push    rsi
0x18001200f  push    rdi
0x180012010  sub     rsp, 90h
0x180012017  mov     rax, cs:__security_cookie
0x18001201e  xor     rax, rsp
0x180012021  mov     [rsp+0A8h+var_28], rax
0x180012029  mov     rbx, rdx
0x18001202c  lea     rcx, [rsp+0A8h+var_68]; void *
0x180012031  xor     edx, edx; Val
0x180012033  mov     rdi, r8
0x180012036  mov     rsi, r9
0x180012039  lea     r8d, [rdx+40h]; Size
0x18001203d  call    memset_0
0x180012042  mov     r8d, 20h ; ' '; unsigned __int64
0x180012048  lea     rdx, [rsp+0A8h+var_68]; unsigned __int16 *
0x18001204d  mov     rcx, rbx; struct _ITEMIDLIST *
0x180012050  call    ?FID_FamilyName@@YAJPEFBU_ITEMIDLIST@@PEAG_K@Z; FID_FamilyName(_ITEMIDLIST const *,ushort *,unsigned __int64)
0x180012055  mov     ebx, eax
0x180012057  test    eax, eax
0x180012059  js      loc_1800120EC
0x18001205f  lea     r9, [rsp+0A8h+var_70]; void **
0x180012064  mov     [rsp+0A8h+var_70], 0
0x18001206d  lea     r8, _GUID_000214f2_0000_0000_c000_000000000046; struct _GUID *
0x180012074  mov     edx, 40h ; '@'; unsigned int
0x180012079  lea     rcx, [rsp+0A8h+var_68]; unsigned __int16 *
0x18001207e  call    ?CreateInstance@CFontFolderEnum@@SAJPEBGKAEBU_GUID@@PEAPEAX@Z; CFontFolderEnum::CreateInstance(ushort const *,ulong,_GUID const &,void * *)
0x180012083  mov     ebx, eax
0x180012085  test    eax, eax
0x180012087  js      short loc_1800120EC
0x180012089  mov     [rsp+0A8h+pv], 0
0x180012092  mov     rcx, [rsp+0A8h+var_70]
0x180012097  lea     r8, [rsp+0A8h+pv]
0x18001209c  xor     r9d, r9d
0x18001209f  mov     rax, [rcx]
0x1800120a2  lea     edx, [r9+1]
0x1800120a6  mov     rax, [rax+18h]
0x1800120aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120af  test    eax, eax
0x1800120b1  jnz     short loc_1800120DB
0x1800120b3  test    ebx, ebx
0x1800120b5  js      short loc_1800120DB
0x1800120b7  mov     rdx, [rsp+0A8h+pv]; struct _ITEMIDLIST *
0x1800120bc  mov     r9, rsi; unsigned int *
0x1800120bf  mov     r8, rdi; unsigned __int16 **
0x1800120c2  call    ?_AddPathNamesToBuffer@CFontFolderData@@AEAAJPEFBU_ITEMIDLIST@@PEAPEAGPEAI@Z; CFontFolderData::_AddPathNamesToBuffer(_ITEMIDLIST const *,ushort * *,uint *)
0x1800120c7  mov     rcx, [rsp+0A8h+pv]; pv
0x1800120cc  mov     ebx, eax
0x1800120ce  test    rcx, rcx
0x1800120d1  jz      short loc_180012092
0x1800120d3  call    cs:__imp_CoTaskMemFree
0x1800120d9  jmp     short loc_180012092
0x1800120db  mov     rcx, [rsp+0A8h+var_70]
0x1800120e0  mov     rax, [rcx]
0x1800120e3  mov     rax, [rax+10h]
0x1800120e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120ec  mov     eax, ebx
0x1800120ee  mov     rcx, [rsp+0A8h+var_28]
0x1800120f6  xor     rcx, rsp; StackCookie
0x1800120f9  call    __security_check_cookie
0x1800120fe  add     rsp, 90h
0x180012105  pop     rdi
0x180012106  pop     rsi
0x180012107  pop     rbx
0x180012108  retn
```
