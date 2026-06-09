# ColorCplSupportUtil::SetUsePerUserProfiles(ushort const *,ulong,int)

- ea: `0x180047230`
- end: `0x1800472f7`
- name: `?SetUsePerUserProfiles@ColorCplSupportUtil@@SAJPEBGKH@Z`
- size: `199`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180046df0`

## callees

- `0x18002e5f0`
- `0x1800471b0`
- `0x180047230`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800472d7`
- `ntdll!EtwEventWrite` at `0x1800472d7`

## pseudocode

```c
__int64 __fastcall ColorCplSupportUtil::SetUsePerUserProfiles(const unsigned __int16 *a1, unsigned int a2, int a3)
{
  int v4; // edi
  __int64 v5; // rcx
  int v6; // ecx
  unsigned __int8 v8[8]; // [rsp+30h] [rbp-38h] BYREF
  const unsigned __int16 *v9; // [rsp+38h] [rbp-30h] BYREF
  int v10; // [rsp+40h] [rbp-28h]
  int v11; // [rsp+44h] [rbp-24h]
  unsigned __int8 *v12; // [rsp+48h] [rbp-20h]
  __int64 v13; // [rsp+50h] [rbp-18h]

  *(_DWORD *)v8 = a3;
  v4 = ColorCplSupportUtil::SetProfileData(WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER, a1, a2, 3u, v8, 4u);
  if ( v4 >= 0 )
  {
    if ( a1 )
    {
      v5 = -1;
      do
        ++v5;
      while ( a1[v5] );
      v6 = 2 * v5 + 2;
    }
    else
    {
      v6 = 0;
    }
    v10 = v6;
    v11 = 0;
    v12 = v8;
    v9 = a1;
    v13 = 4;
    EtwEventWrite(g_etwHandle, SET_USE_PER_USER_PROFILES, 2, &v9);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180047230  mov     r11, rsp
0x180047233  mov     [r11+10h], rbx
0x180047237  push    rdi
0x180047238  sub     rsp, 60h
0x18004723c  mov     rax, cs:__security_cookie
0x180047243  xor     rax, rsp
0x180047246  mov     [rsp+68h+var_10], rax
0x18004724b  mov     r9d, 3; unsigned int
0x180047251  mov     [r11-38h], r8d
0x180047255  mov     r8d, edx; unsigned int
0x180047258  mov     [rsp+68h+var_40], 4; unsigned int
0x180047260  mov     rbx, rcx
0x180047263  lea     rax, [r11-38h]
0x180047267  mov     rdx, rcx; unsigned __int16 *
0x18004726a  mov     [r11-48h], rax
0x18004726e  lea     ecx, [r9-2]; enum WCS_PROFILE_MANAGEMENT_SCOPE
0x180047272  call    ?SetProfileData@ColorCplSupportUtil@@CAJW4WCS_PROFILE_MANAGEMENT_SCOPE@@PEBGKKPEAEK@Z; ColorCplSupportUtil::SetProfileData(WCS_PROFILE_MANAGEMENT_SCOPE,ushort const *,ulong,ulong,uchar *,ulong)
0x180047277  xor     edx, edx
0x180047279  mov     edi, eax
0x18004727b  test    eax, eax
0x18004727d  js      short loc_1800472DD
0x18004727f  test    rbx, rbx
0x180047282  jz      short loc_18004729B
0x180047284  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180047288  inc     rcx
0x18004728b  cmp     [rbx+rcx*2], dx
0x18004728f  jnz     short loc_180047288
0x180047291  lea     rcx, ds:2[rcx*2]
0x180047299  jmp     short loc_18004729E
0x18004729b  mov     rcx, rdx
0x18004729e  mov     [rsp+68h+var_28], ecx
0x1800472a2  lea     rax, [rsp+68h+var_38]
0x1800472a7  mov     rcx, cs:g_etwHandle
0x1800472ae  lea     r9, [rsp+68h+var_30]
0x1800472b3  mov     [rsp+68h+var_24], edx
0x1800472b7  mov     r8d, 2
0x1800472bd  lea     rdx, SET_USE_PER_USER_PROFILES
0x1800472c4  mov     [rsp+68h+var_20], rax
0x1800472c9  mov     [rsp+68h+var_30], rbx
0x1800472ce  mov     [rsp+68h+var_18], 4
0x1800472d7  call    cs:__imp_EtwEventWrite
0x1800472dd  mov     eax, edi
0x1800472df  mov     rcx, [rsp+68h+var_10]
0x1800472e4  xor     rcx, rsp; StackCookie
0x1800472e7  call    __security_check_cookie
0x1800472ec  mov     rbx, [rsp+68h+arg_8]
0x1800472f1  add     rsp, 60h
0x1800472f5  pop     rdi
0x1800472f6  retn
```
