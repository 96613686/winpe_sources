# ClasspMediaChangeRegistryCallBack

- ea: `0x140055850`
- end: `0x1400559e1`
- name: `ClasspMediaChangeRegistryCallBack`
- size: `401`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14001fc38`
- `0x14001feac`
- `0x140055850`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140055913`
- `ntoskrnl!RtlCompareMemory` at `0x140055913`

## pseudocode

```c
__int64 __fastcall ClasspMediaChangeRegistryCallBack(
        __int64 a1,
        int a2,
        const void *a3,
        int a4,
        unsigned __int16 *a5,
        _DWORD *a6)
{
  PDEVICE_OBJECT v7; // rcx
  __int64 v8; // rdx
  unsigned int v10; // eax

  if ( a3 && a5 && a6 )
  {
    if ( *a6 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        return 0;
      }
      v8 = 93;
    }
    else
    {
      if ( a4 != 2 )
      {
        if ( a2 == 1 )
        {
          v10 = *a5;
          if ( a4 - 2 <= v10 )
            v10 = a4 - 2;
          if ( RtlCompareMemory(*((const void **)a5 + 1), a3, v10) == v10 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            {
              if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 95, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids);
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              {
                if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                  WPP_SF_q(
                    WPP_GLOBAL_Control->AttachedDevice,
                    96,
                    WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids,
                    *((_QWORD *)a5 + 1));
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 97, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids, a3);
                }
              }
            }
            *a6 = 1;
          }
        }
        return 0;
      }
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
      {
        return 0;
      }
      v8 = 94;
    }
    WPP_SF_(v7->AttachedDevice, v8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids);
    return 0;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x140055850  push    rbx
0x140055852  push    rbp
0x140055853  push    rsi
0x140055854  push    r14
0x140055856  sub     rsp, 28h
0x14005585a  mov     r14, r8
0x14005585d  test    r8, r8
0x140055860  jz      loc_1400559D1
0x140055866  mov     rbp, [rsp+48h+arg_20]
0x14005586b  test    rbp, rbp
0x14005586e  jz      loc_1400559D1
0x140055874  mov     rsi, [rsp+48h+arg_28]
0x140055879  test    rsi, rsi
0x14005587c  jz      loc_1400559D1
0x140055882  cmp     dword ptr [rsi], 0
0x140055885  jz      short loc_1400558B0
0x140055887  mov     rcx, cs:WPP_GLOBAL_Control
0x14005588e  lea     rbx, WPP_GLOBAL_Control
0x140055895  cmp     rcx, rbx
0x140055898  jz      short loc_1400558F3
0x14005589a  test    dword ptr [rcx+2Ch], 1000h
0x1400558a1  jz      short loc_1400558F3
0x1400558a3  cmp     byte ptr [rcx+29h], 4
0x1400558a7  jb      short loc_1400558F3
0x1400558a9  mov     edx, 5Dh ; ']'
0x1400558ae  jmp     short loc_1400558DC
0x1400558b0  cmp     r9d, 2
0x1400558b4  jnz     short loc_1400558EE
0x1400558b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400558bd  lea     rbx, WPP_GLOBAL_Control
0x1400558c4  cmp     rcx, rbx
0x1400558c7  jz      short loc_1400558F3
0x1400558c9  test    dword ptr [rcx+2Ch], 1000h
0x1400558d0  jz      short loc_1400558F3
0x1400558d2  cmp     byte ptr [rcx+29h], 3
0x1400558d6  jb      short loc_1400558F3
0x1400558d8  lea     edx, [r9+5Ch]
0x1400558dc  mov     rcx, [rcx+18h]
0x1400558e0  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x1400558e7  call    WPP_SF_
0x1400558ec  jmp     short loc_1400558F3
0x1400558ee  cmp     edx, 1
0x1400558f1  jz      short loc_1400558FA
0x1400558f3  xor     eax, eax
0x1400558f5  jmp     loc_1400559D6
0x1400558fa  movzx   eax, word ptr [rbp+0]
0x1400558fe  lea     ecx, [r9-2]
0x140055902  cmp     ecx, eax
0x140055904  mov     rdx, r14; Source2
0x140055907  cmovbe  eax, ecx
0x14005590a  mov     rcx, [rbp+8]; Source1
0x14005590e  mov     r8d, eax; Length
0x140055911  mov     ebx, eax
0x140055913  call    cs:__imp_RtlCompareMemory
0x14005591a  nop     dword ptr [rax+rax+00h]
0x14005591f  cmp     rax, rbx
0x140055922  jnz     short loc_1400558F3
0x140055924  mov     rcx, cs:WPP_GLOBAL_Control
0x14005592b  lea     rbx, WPP_GLOBAL_Control
0x140055932  cmp     rcx, rbx
0x140055935  jz      loc_1400559C6
0x14005593b  test    dword ptr [rcx+2Ch], 1000h
0x140055942  jz      short loc_14005595F
0x140055944  cmp     byte ptr [rcx+29h], 4
0x140055948  jb      short loc_14005595F
0x14005594a  mov     rcx, [rcx+18h]
0x14005594e  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x140055955  mov     edx, 5Fh ; '_'
0x14005595a  call    WPP_SF_
0x14005595f  mov     rcx, cs:WPP_GLOBAL_Control
0x140055966  cmp     rcx, rbx
0x140055969  jz      short loc_1400559C6
0x14005596b  test    dword ptr [rcx+2Ch], 1000h
0x140055972  jz      short loc_140055993
0x140055974  cmp     byte ptr [rcx+29h], 4
0x140055978  jb      short loc_140055993
0x14005597a  mov     r9, [rbp+8]
0x14005597e  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x140055985  mov     rcx, [rcx+18h]
0x140055989  mov     edx, 60h ; '`'
0x14005598e  call    WPP_SF_q
0x140055993  mov     rcx, cs:WPP_GLOBAL_Control
0x14005599a  cmp     rcx, rbx
0x14005599d  jz      short loc_1400559C6
0x14005599f  test    dword ptr [rcx+2Ch], 1000h
0x1400559a6  jz      short loc_1400559C6
0x1400559a8  cmp     byte ptr [rcx+29h], 4
0x1400559ac  jb      short loc_1400559C6
0x1400559ae  mov     rcx, [rcx+18h]
0x1400559b2  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x1400559b9  mov     edx, 61h ; 'a'
0x1400559be  mov     r9, r14
0x1400559c1  call    WPP_SF_q
0x1400559c6  mov     dword ptr [rsi], 1
0x1400559cc  jmp     loc_1400558F3
0x1400559d1  mov     eax, 0C000000Dh
0x1400559d6  add     rsp, 28h
0x1400559da  pop     r14
0x1400559dc  pop     rsi
0x1400559dd  pop     rbp
0x1400559de  pop     rbx
0x1400559df  retn
```
