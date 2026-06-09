# LipsStateIkeFilterDeleteCb

- ea: `0x180045930`
- end: `0x1800459eb`
- name: `LipsStateIkeFilterDeleteCb`
- size: `187`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000c4d0`
- `0x18000e510`
- `0x180045930`
- `0x180047f60`
- `0x1800482dc`

## string_xrefs

- `0x1800459ce`: `LipsStateIkeFilterDeleteCb`

## pseudocode

```c
__int64 __fastcall LipsStateIkeFilterDeleteCb(__int64 a1)
{
  unsigned int v1; // ebx
  GUID ***v2; // rdi
  GUID **v3; // rax
  _QWORD *v4; // rcx
  __int64 v5; // rdx

  v1 = 0;
  v2 = (GUID ***)(a1 + 184);
  if ( a1 != -184 )
  {
    v3 = *v2;
    if ( *v2 )
    {
      if ( *v3 )
      {
        v1 = LipsBfeFilterDelete(*v3);
        if ( v1 )
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          {
            return (unsigned int)LipsReportError(v1, (int)"LipsStateIkeFilterDeleteCb");
          }
          v5 = 26;
LABEL_12:
          WPP_SF_d(v4[2], v5, WPP_b2e62c343c9f3927bd54de5c93575086_Traceguids, v1);
          return (unsigned int)LipsReportError(v1, (int)"LipsStateIkeFilterDeleteCb");
        }
      }
      v1 = LipsBfeProviderContextDelete((GUID *)(*v2 + 1));
      if ( v1 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          return (unsigned int)LipsReportError(v1, (int)"LipsStateIkeFilterDeleteCb");
        v5 = 27;
        goto LABEL_12;
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180045930  mov     [rsp+arg_0], rbx
0x180045935  push    rdi
0x180045936  sub     rsp, 20h
0x18004593a  xor     ebx, ebx
0x18004593c  lea     rdi, [rcx+0B8h]
0x180045943  test    rdi, rdi
0x180045946  jz      loc_1800459DE
0x18004594c  mov     rax, [rdi]
0x18004594f  test    rax, rax
0x180045952  jz      loc_1800459DE
0x180045958  mov     rcx, [rax]; key
0x18004595b  test    rcx, rcx
0x18004595e  jz      short loc_18004598B
0x180045960  call    LipsBfeFilterDelete
0x180045965  mov     ebx, eax
0x180045967  test    eax, eax
0x180045969  jz      short loc_18004598B
0x18004596b  mov     rcx, cs:WPP_GLOBAL_Control
0x180045972  lea     rax, WPP_GLOBAL_Control
0x180045979  cmp     rcx, rax
0x18004597c  jz      short loc_1800459CE
0x18004597e  test    byte ptr [rcx+1Ch], 10h
0x180045982  jz      short loc_1800459CE
0x180045984  mov     edx, 1Ah
0x180045989  jmp     short loc_1800459BB
0x18004598b  mov     rcx, [rdi]
0x18004598e  add     rcx, 8; key
0x180045992  call    LipsBfeProviderContextDelete
0x180045997  mov     ebx, eax
0x180045999  test    eax, eax
0x18004599b  jz      short loc_1800459DE
0x18004599d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800459a4  lea     rax, WPP_GLOBAL_Control
0x1800459ab  cmp     rcx, rax
0x1800459ae  jz      short loc_1800459CE
0x1800459b0  test    byte ptr [rcx+1Ch], 10h
0x1800459b4  jz      short loc_1800459CE
0x1800459b6  mov     edx, 1Bh
0x1800459bb  mov     rcx, [rcx+10h]
0x1800459bf  lea     r8, WPP_b2e62c343c9f3927bd54de5c93575086_Traceguids
0x1800459c6  mov     r9d, ebx
0x1800459c9  call    WPP_SF_d
0x1800459ce  lea     rdx, aLipsstateikefi_2; "LipsStateIkeFilterDeleteCb"
0x1800459d5  mov     ecx, ebx
0x1800459d7  call    LipsReportError
0x1800459dc  mov     ebx, eax
0x1800459de  mov     eax, ebx
0x1800459e0  mov     rbx, [rsp+28h+arg_0]
0x1800459e5  add     rsp, 20h
0x1800459e9  pop     rdi
0x1800459ea  retn
```
