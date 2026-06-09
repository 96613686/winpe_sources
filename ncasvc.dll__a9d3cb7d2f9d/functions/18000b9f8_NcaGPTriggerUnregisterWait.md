# NcaGPTriggerUnregisterWait

- ea: `0x18000b9f8`
- end: `0x18000bad5`
- name: `NcaGPTriggerUnregisterWait`
- size: `221`
- prototype: `__int64 __fastcall(_DWORD *lpMem)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180006b10`
- `0x18000b88c`
- `0x180010270`
- `0x180014520`

## callees

- `0x180003770`
- `0x180004f04`
- `0x180004f34`
- `0x18000b6d8`
- `0x18000b9f8`

## import_xrefs

- `USERENV!UnregisterGPNotification` at `0x18000ba79`
- `USERENV!UnregisterGPNotification` at `0x18000ba79`

## pseudocode

```c
__int64 __fastcall NcaGPTriggerUnregisterWait(_DWORD *lpMem)
{
  PVOID *v2; // rcx
  unsigned int v3; // edi

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_6469918148f530adab9bf1aa7ae01e8e_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( lpMem )
  {
    v3 = 0;
    if ( lpMem[2] == 1 )
    {
      UnregisterGPNotification(*(HANDLE *)(*(_QWORD *)lpMem + 8LL));
      lpMem[2] = 0;
    }
    NcaTriggerUnregisterWait(*(LPVOID *)lpMem);
    NcaFree(lpMem);
    goto LABEL_11;
  }
  v3 = 87;
  if ( v2 == &WPP_GLOBAL_Control )
    return v3;
  if ( (*((_BYTE *)v2 + 28) & 1) != 0 )
  {
    WPP_SF_d(v2[2], 16, WPP_6469918148f530adab9bf1aa7ae01e8e_Traceguids, 87);
LABEL_11:
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
    WPP_SF_d(v2[2], 17, WPP_6469918148f530adab9bf1aa7ae01e8e_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x18000b9f8  mov     [rsp+arg_0], rbx
0x18000b9fd  mov     [rsp+arg_8], rsi
0x18000ba02  push    rdi
0x18000ba03  sub     rsp, 20h
0x18000ba07  mov     rbx, rcx
0x18000ba0a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ba11  lea     rsi, WPP_GLOBAL_Control
0x18000ba18  cmp     rcx, rsi
0x18000ba1b  jz      short loc_18000BA3F
0x18000ba1d  test    byte ptr [rcx+1Ch], 8
0x18000ba21  jz      short loc_18000BA3F
0x18000ba23  mov     rcx, [rcx+10h]
0x18000ba27  lea     r8, WPP_6469918148f530adab9bf1aa7ae01e8e_Traceguids
0x18000ba2e  mov     edx, 0Fh
0x18000ba33  call    WPP_SF_
0x18000ba38  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ba3f  test    rbx, rbx
0x18000ba42  jnz     short loc_18000BA6A
0x18000ba44  lea     edi, [rbx+57h]
0x18000ba47  cmp     rcx, rsi
0x18000ba4a  jz      short loc_18000BAC2
0x18000ba4c  test    byte ptr [rcx+1Ch], 1
0x18000ba50  jz      short loc_18000BA9F
0x18000ba52  mov     rcx, [rcx+10h]
0x18000ba56  lea     edx, [rbx+10h]
0x18000ba59  mov     r9d, edi
0x18000ba5c  lea     r8, WPP_6469918148f530adab9bf1aa7ae01e8e_Traceguids
0x18000ba63  call    WPP_SF_d
0x18000ba68  jmp     short loc_18000BA98
0x18000ba6a  xor     edi, edi
0x18000ba6c  cmp     dword ptr [rbx+8], 1
0x18000ba70  jnz     short loc_18000BA88
0x18000ba72  mov     rcx, [rbx]
0x18000ba75  mov     rcx, [rcx+8]; hEvent
0x18000ba79  call    cs:__imp_UnregisterGPNotification
0x18000ba80  nop     dword ptr [rax+rax+00h]
0x18000ba85  mov     [rbx+8], edi
0x18000ba88  mov     rcx, [rbx]; lpMem
0x18000ba8b  call    NcaTriggerUnregisterWait
0x18000ba90  mov     rcx, rbx; lpMem
0x18000ba93  call    NcaFree
0x18000ba98  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ba9f  cmp     rcx, rsi
0x18000baa2  jz      short loc_18000BAC2
0x18000baa4  test    byte ptr [rcx+1Ch], 8
0x18000baa8  jz      short loc_18000BAC2
0x18000baaa  mov     rcx, [rcx+10h]
0x18000baae  lea     r8, WPP_6469918148f530adab9bf1aa7ae01e8e_Traceguids
0x18000bab5  mov     edx, 11h
0x18000baba  mov     r9d, edi
0x18000babd  call    WPP_SF_d
0x18000bac2  mov     rbx, [rsp+28h+arg_0]
0x18000bac7  mov     eax, edi
0x18000bac9  mov     rsi, [rsp+28h+arg_8]
0x18000bace  add     rsp, 20h
0x18000bad2  pop     rdi
0x18000bad3  retn
```
