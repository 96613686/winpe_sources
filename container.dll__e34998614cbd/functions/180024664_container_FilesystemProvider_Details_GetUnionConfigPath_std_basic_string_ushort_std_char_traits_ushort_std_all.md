# container::FilesystemProvider::Details::GetUnionConfigPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180024664`
- end: `0x1800246f8`
- name: `?GetUnionConfigPath@Details@FilesystemProvider@container@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV45@@Z`
- size: `148`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800243c4`
- `0x180024a84`

## callees

- `0x180004c40`
- `0x180023e64`
- `0x180024208`
- `0x180024664`

## string_xrefs

- `0x1800246df`: `Windows\container_tombstones.json`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall container::FilesystemProvider::Details::GetUnionConfigPath(_QWORD *Src, __int64 a2)
{
  __int64 v3; // rdx
  unsigned __int64 v4; // rcx
  _WORD *v5; // rax
  _QWORD *v6; // rcx

  std::wstring::wstring(Src, a2);
  v3 = Src[2];
  if ( v3 )
  {
    v4 = Src[3];
    v5 = v4 <= 7 ? Src : (_WORD *)*Src;
    if ( v5[v3 - 1] != 92 )
    {
      if ( v4 == v3 )
      {
        std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,unsigned short>(Src);
      }
      else
      {
        Src[2] = v3 + 1;
        if ( v4 <= 7 )
          v6 = Src;
        else
          v6 = (_QWORD *)*Src;
        *(_DWORD *)((char *)v6 + 2 * v3) = 92;
      }
    }
  }
  std::wstring::append(Src, L"Windows\\container_tombstones.json");
  return Src;
}

```

## disassembly

```asm
0x180024664  mov     [rsp+arg_0], rcx
0x180024669  push    rbx
0x18002466a  sub     rsp, 40h
0x18002466e  mov     rbx, rcx
0x180024671  mov     [rsp+48h+var_18], 0
0x180024679  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002467e  mov     [rsp+48h+var_18], 1
0x180024686  mov     rdx, [rbx+10h]
0x18002468a  test    rdx, rdx
0x18002468d  jz      short loc_1800246DF
0x18002468f  mov     rcx, [rbx+18h]
0x180024693  cmp     rcx, 7
0x180024697  jbe     short loc_18002469E
0x180024699  mov     rax, [rbx]
0x18002469c  jmp     short loc_1800246A1
0x18002469e  mov     rax, rbx
0x1800246a1  mov     r8d, 5Ch ; '\'
0x1800246a7  cmp     [rax+rdx*2-2], r8w
0x1800246ad  jz      short loc_1800246DF
0x1800246af  mov     rax, rcx
0x1800246b2  sub     rax, rdx
0x1800246b5  cmp     rax, 1
0x1800246b9  jb      short loc_1800246D7
0x1800246bb  lea     rax, [rdx+1]
0x1800246bf  mov     [rbx+10h], rax
0x1800246c3  cmp     rcx, 7
0x1800246c7  jbe     short loc_1800246CE
0x1800246c9  mov     rcx, [rbx]
0x1800246cc  jmp     short loc_1800246D1
0x1800246ce  mov     rcx, rbx
0x1800246d1  mov     [rcx+rdx*2], r8d
0x1800246d5  jmp     short loc_1800246DF
0x1800246d7  mov     rcx, rbx; Src
0x1800246da  call    ??$_Reallocate_grow_by@V_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@Z; std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort>(unsigned __int64,_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort)
0x1800246df  lea     rdx, aWindowsContain_0; "Windows\\container_tombstones.json"
0x1800246e6  mov     rcx, rbx; Src
0x1800246e9  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800246ee  mov     rax, rbx
0x1800246f1  add     rsp, 40h
0x1800246f5  pop     rbx
0x1800246f6  retn
```
