# DfdCollector::WriteEvent(_EVENT_DESCRIPTOR const *)

- ea: `0x180007bc0`
- end: `0x180007c63`
- name: `?WriteEvent@DfdCollector@@AEAAXPEBU_EVENT_DESCRIPTOR@@@Z`
- size: `163`
- prototype: `void __fastcall(REGHANDLE *this, const struct _EVENT_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002450`

## callees

- `0x180002c68`
- `0x180002c90`
- `0x180007bc0`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x180007bf2`
- `ADVAPI32!EventWrite` at `0x180007bf2`

## pseudocode

```c
void __fastcall DfdCollector::WriteEvent(REGHANDLE *this, const struct _EVENT_DESCRIPTOR *a2)
{
  REGHANDLE v2; // rcx
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  ULONG v5; // eax

  v2 = *this;
  if ( v2 )
  {
    v5 = EventWrite(v2, a2, 0, 0);
    if ( v5 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_7cd7c10ab54f3ad41c442ebb2d0f47f1_Traceguids, v5);
    }
    else
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v4 = v5 + 18;
        goto LABEL_9;
      }
    }
  }
  else
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v4 = 17;
LABEL_9:
      WPP_SF_(v3[2], v4, WPP_7cd7c10ab54f3ad41c442ebb2d0f47f1_Traceguids);
    }
  }
}

```

## disassembly

```asm
0x180007bc0  sub     rsp, 28h
0x180007bc4  mov     rcx, [rcx]; RegHandle
0x180007bc7  test    rcx, rcx
0x180007bca  jnz     short loc_180007BEC
0x180007bcc  mov     rcx, cs:WPP_GLOBAL_Control
0x180007bd3  lea     rax, WPP_GLOBAL_Control
0x180007bda  cmp     rcx, rax
0x180007bdd  jz      short loc_180007C5E
0x180007bdf  test    byte ptr [rcx+1Ch], 4
0x180007be3  jz      short loc_180007C5E
0x180007be5  mov     edx, 11h; EventDescriptor
0x180007bea  jmp     short loc_180007C1C
0x180007bec  xor     r9d, r9d; UserData
0x180007bef  xor     r8d, r8d; UserDataCount
0x180007bf2  call    cs:__imp_EventWrite
0x180007bf8  mov     r9d, eax
0x180007bfb  test    eax, eax
0x180007bfd  jnz     short loc_180007C30
0x180007bff  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c06  lea     rax, WPP_GLOBAL_Control
0x180007c0d  cmp     rcx, rax
0x180007c10  jz      short loc_180007C5E
0x180007c12  test    byte ptr [rcx+1Ch], 4
0x180007c16  jz      short loc_180007C5E
0x180007c18  lea     edx, [r9+12h]
0x180007c1c  mov     rcx, [rcx+10h]
0x180007c20  lea     r8, WPP_7cd7c10ab54f3ad41c442ebb2d0f47f1_Traceguids
0x180007c27  add     rsp, 28h
0x180007c2b  jmp     WPP_SF_
0x180007c30  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c37  lea     rax, WPP_GLOBAL_Control
0x180007c3e  cmp     rcx, rax
0x180007c41  jz      short loc_180007C5E
0x180007c43  test    byte ptr [rcx+1Ch], 1
0x180007c47  jz      short loc_180007C5E
0x180007c49  mov     rcx, [rcx+10h]
0x180007c4d  lea     r8, WPP_7cd7c10ab54f3ad41c442ebb2d0f47f1_Traceguids
0x180007c54  mov     edx, 13h
0x180007c59  call    WPP_SF_d
0x180007c5e  add     rsp, 28h
0x180007c62  retn
```
