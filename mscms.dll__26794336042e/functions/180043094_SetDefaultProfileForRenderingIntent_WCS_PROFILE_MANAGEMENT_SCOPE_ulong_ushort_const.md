# SetDefaultProfileForRenderingIntent(WCS_PROFILE_MANAGEMENT_SCOPE,ulong,ushort const *)

- ea: `0x180043094`
- end: `0x18004319d`
- name: `?SetDefaultProfileForRenderingIntent@@YAKW4WCS_PROFILE_MANAGEMENT_SCOPE@@KPEBG@Z`
- size: `265`
- prototype: `unsigned int __fastcall(enum WCS_PROFILE_MANAGEMENT_SCOPE, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18002435c`

## callees

- `0x18002e5f0`
- `0x180043094`
- `0x18004387c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180043179`
- `ntdll!EtwEventWrite` at `0x180043179`

## pseudocode

```c
__int64 __fastcall SetDefaultProfileForRenderingIntent(
        enum WCS_PROFILE_MANAGEMENT_SCOPE a1,
        int a2,
        const unsigned __int16 *a3)
{
  int v4; // edx
  int v5; // edx
  unsigned int v6; // edi
  unsigned int v7; // edx
  unsigned int v8; // r8d
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 *v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rcx
  enum WCS_PROFILE_MANAGEMENT_SCOPE v15; // [rsp+20h] [rbp-40h] BYREF
  int *v16; // [rsp+28h] [rbp-38h] BYREF
  _QWORD v17[2]; // [rsp+30h] [rbp-30h]
  int v18; // [rsp+40h] [rbp-20h]
  int v19; // [rsp+44h] [rbp-1Ch]
  int v20; // [rsp+88h] [rbp+28h] BYREF

  v20 = a2;
  v15 = a1;
  if ( a2 )
  {
    v4 = a2 - 1;
    if ( v4 )
    {
      v5 = v4 - 1;
      if ( v5 )
      {
        if ( v5 != 1 )
          return 87;
        v7 = 1919508835;
      }
      else
      {
        v7 = 1919513344;
      }
    }
    else
    {
      v7 = 1919513187;
    }
  }
  else
  {
    v7 = 1919512576;
  }
  v6 = SetProfileForProfileID(a1, v7, a3, 0);
  if ( !v6 )
  {
    v17[0] = 4;
    v8 = 1;
    v16 = &v20;
    if ( a3 )
    {
      v9 = -1;
      do
        ++v9;
      while ( a3[v9] );
      v17[1] = a3;
      v18 = 2 * v9 + 2;
      v8 = 2;
      v19 = 0;
    }
    v10 = 2LL * v8;
    v11 = SET_DEFAULT_PROFILE_FOR_RENDERING_INTENT;
    v12 = v8 + 1;
    v17[v10 - 1] = &v15;
    v13 = g_etwHandle;
    v17[v10] = 4;
    if ( !a3 )
      v11 = UNSET_DEFAULT_PROFILE_FOR_RENDERING_INTENT;
    EtwEventWrite(v13, v11, v12, &v16);
  }
  return v6;
}

```

## disassembly

```asm
0x180043094  mov     [rsp-18h+arg_18], rbx
0x180043099  mov     [rsp-18h+arg_8], edx
0x18004309d  push    rbp
0x18004309e  push    rsi
0x18004309f  push    rdi
0x1800430a0  mov     rbp, rsp
0x1800430a3  sub     rsp, 60h
0x1800430a7  mov     rax, cs:__security_cookie
0x1800430ae  xor     rax, rsp
0x1800430b1  mov     [rbp+var_8], rax
0x1800430b5  xor     esi, esi
0x1800430b7  mov     [rbp+var_40], ecx
0x1800430ba  mov     rbx, r8
0x1800430bd  test    edx, edx
0x1800430bf  jz      short loc_1800430ED
0x1800430c1  sub     edx, 1
0x1800430c4  jz      short loc_1800430E6
0x1800430c6  sub     edx, 1
0x1800430c9  jz      short loc_1800430DF
0x1800430cb  cmp     edx, 1
0x1800430ce  jz      short loc_1800430D8
0x1800430d0  lea     edi, [rsi+57h]
0x1800430d3  jmp     loc_18004317F
0x1800430d8  mov     edx, 72696163h
0x1800430dd  jmp     short loc_1800430F2
0x1800430df  mov     edx, 72697300h
0x1800430e4  jmp     short loc_1800430F2
0x1800430e6  mov     edx, 72697263h
0x1800430eb  jmp     short loc_1800430F2
0x1800430ed  mov     edx, 72697000h; unsigned int
0x1800430f2  xor     r9d, r9d; int
0x1800430f5  call    ?SetProfileForProfileID@@YAKW4WCS_PROFILE_MANAGEMENT_SCOPE@@KPEBGH@Z; SetProfileForProfileID(WCS_PROFILE_MANAGEMENT_SCOPE,ulong,ushort const *,int)
0x1800430fa  mov     edi, eax
0x1800430fc  test    eax, eax
0x1800430fe  jnz     short loc_18004317F
0x180043100  mov     [rbp+var_30], 4
0x180043108  lea     r8d, [rax+1]
0x18004310c  lea     rax, [rbp+arg_8]
0x180043110  mov     [rbp+var_38], rax
0x180043114  test    rbx, rbx
0x180043117  jz      short loc_18004313E
0x180043119  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004311d  inc     rax
0x180043120  cmp     [rbx+rax*2], si
0x180043124  jnz     short loc_18004311D
0x180043126  lea     rax, ds:2[rax*2]
0x18004312e  mov     [rbp+var_28], rbx
0x180043132  mov     [rbp+var_20], eax
0x180043135  mov     r8d, 2
0x18004313b  mov     [rbp+var_1C], esi
0x18004313e  mov     eax, r8d
0x180043141  lea     rcx, [rbp+var_40]
0x180043145  add     rax, rax
0x180043148  lea     rdx, SET_DEFAULT_PROFILE_FOR_RENDERING_INTENT
0x18004314f  inc     r8d
0x180043152  lea     r9, [rbp+var_38]
0x180043156  test    rbx, rbx
0x180043159  mov     [rbp+rax*8+var_38], rcx
0x18004315e  mov     rcx, cs:g_etwHandle
0x180043165  mov     [rbp+rax*8+var_30], 4
0x18004316e  lea     rax, UNSET_DEFAULT_PROFILE_FOR_RENDERING_INTENT
0x180043175  cmovz   rdx, rax
0x180043179  call    cs:__imp_EtwEventWrite
0x18004317f  mov     eax, edi
0x180043181  mov     rcx, [rbp+var_8]
0x180043185  xor     rcx, rsp; StackCookie
0x180043188  call    __security_check_cookie
0x18004318d  mov     rbx, [rsp+60h+arg_18]
0x180043195  add     rsp, 60h
0x180043199  pop     rdi
0x18004319a  pop     rsi
0x18004319b  pop     rbp
0x18004319c  retn
```
