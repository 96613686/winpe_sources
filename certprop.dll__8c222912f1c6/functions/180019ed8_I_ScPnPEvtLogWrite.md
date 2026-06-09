# I_ScPnPEvtLogWrite

- ea: `0x180019ed8`
- end: `0x180019f9d`
- name: `I_ScPnPEvtLogWrite`
- size: `197`
- prototype: `__int64 __fastcall(PCEVENT_DESCRIPTOR EventDescriptor, __int64, struct _EVENT_DATA_DESCRIPTOR *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18001913c`
- `0x18001a5d0`

## callees

- `0x180004600`
- `0x180018bb4`
- `0x180019e50`
- `0x180019ed8`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180019f3c`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180019f3c`

## pseudocode

```c
__int64 __fastcall I_ScPnPEvtLogWrite(
        PCEVENT_DESCRIPTOR EventDescriptor,
        __int64 a2,
        struct _EVENT_DATA_DESCRIPTOR *a3)
{
  __int64 v5; // rcx
  ULONG v6; // edi
  STRSAFE_LPSTR v7; // rcx
  int v8; // edx
  __int64 v9; // rcx

  v6 = I_ScPnPEvtLogInitialize();
  if ( v6 )
  {
    WppTraceIndent(v5, 2);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
    {
      v8 = 56;
LABEL_11:
      WPP_SF_sD(
        *((_QWORD *)v7 + 2),
        v8,
        (unsigned int)&WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
        WPP_pszIndent,
        v6);
    }
  }
  else
  {
    v6 = EventWrite(g_hPublisher, EventDescriptor, 2u, a3);
    if ( v6 )
    {
      WppTraceIndent(v9, 2);
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[28] & 1) != 0
        && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
      {
        v8 = 57;
        goto LABEL_11;
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180019ed8  mov     [rsp+arg_0], rbx
0x180019edd  mov     [rsp+arg_8], rsi
0x180019ee2  push    rdi
0x180019ee3  sub     rsp, 30h
0x180019ee7  mov     rbx, r8
0x180019eea  mov     rsi, rcx
0x180019eed  call    I_ScPnPEvtLogInitialize
0x180019ef2  mov     edi, eax
0x180019ef4  test    eax, eax
0x180019ef6  jz      short loc_180019F27
0x180019ef8  mov     ebx, 2
0x180019efd  mov     edx, ebx
0x180019eff  call    WppTraceIndent
0x180019f04  mov     rcx, cs:WPP_GLOBAL_Control
0x180019f0b  lea     rax, WPP_GLOBAL_Control
0x180019f12  cmp     rcx, rax
0x180019f15  jz      short loc_180019F8B
0x180019f17  test    byte ptr [rcx+1Ch], 1
0x180019f1b  jz      short loc_180019F8B
0x180019f1d  cmp     [rcx+19h], bl
0x180019f20  jb      short loc_180019F8B
0x180019f22  lea     edx, [rbx+36h]
0x180019f25  jmp     short loc_180019F70
0x180019f27  mov     rcx, cs:g_hPublisher; RegHandle
0x180019f2e  mov     r9, rbx; UserData
0x180019f31  mov     ebx, 2
0x180019f36  mov     rdx, rsi; EventDescriptor
0x180019f39  mov     r8d, ebx; UserDataCount
0x180019f3c  call    cs:__imp_EventWrite
0x180019f42  mov     edi, eax
0x180019f44  test    eax, eax
0x180019f46  jz      short loc_180019F8B
0x180019f48  mov     edx, ebx
0x180019f4a  call    WppTraceIndent
0x180019f4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180019f56  lea     rax, WPP_GLOBAL_Control
0x180019f5d  cmp     rcx, rax
0x180019f60  jz      short loc_180019F8B
0x180019f62  test    byte ptr [rcx+1Ch], 1
0x180019f66  jz      short loc_180019F8B
0x180019f68  cmp     [rcx+19h], bl
0x180019f6b  jb      short loc_180019F8B
0x180019f6d  lea     edx, [rbx+37h]
0x180019f70  mov     r9, cs:WPP_pszIndent
0x180019f77  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
0x180019f7e  mov     rcx, [rcx+10h]
0x180019f82  mov     [rsp+38h+var_18], edi
0x180019f86  call    WPP_SF_sD
0x180019f8b  mov     rbx, [rsp+38h+arg_0]
0x180019f90  mov     eax, edi
0x180019f92  mov     rsi, [rsp+38h+arg_8]
0x180019f97  add     rsp, 30h
0x180019f9b  pop     rdi
0x180019f9c  retn
```
