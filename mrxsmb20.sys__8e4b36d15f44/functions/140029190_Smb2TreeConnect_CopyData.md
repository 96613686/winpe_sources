# Smb2TreeConnect_CopyData

- ea: `0x140029190`
- end: `0x140029244`
- name: `Smb2TreeConnect_CopyData`
- size: `180`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x1400290f8`
- `0x140029190`
- `0x140029668`
- `0x1400297fc`

## import_xrefs

- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x14002922c`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x14002922c`

## pseudocode

```c
__int64 __fastcall Smb2TreeConnect_CopyData(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v6; // ebp
  int v7; // edi

  if ( a2 == a1 + 2416 )
  {
    if ( (unsigned int)a3 >= *(_DWORD *)(a2 + 748) )
    {
      v6 = 0;
      if ( Smb2ValidateNegotiateInfo(*(_QWORD *)(a2 + 712), *(_QWORD *)(a1 + 72), a3) )
      {
        v7 = 0;
LABEL_11:
        SmbCseUpdateBufferContextStatus(a2, __PAIR64__(v7, v6));
        return 0;
      }
    }
    else
    {
      v6 = -1073741629;
    }
    v7 = 13;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        13,
        WPP_bbbb5ecce09d378367c344661863d2d2_Traceguids,
        *(_QWORD *)(a1 + 72));
    }
    Smb2ProcessNegotiateValidationFailure(a1, a2, a3, a4);
    goto LABEL_11;
  }
  return 0;
}

```

## disassembly

```asm
0x140029190  push    rbx
0x140029192  push    rbp
0x140029193  push    rsi
0x140029194  push    rdi
0x140029195  sub     rsp, 28h
0x140029199  lea     rax, [rcx+970h]
0x1400291a0  mov     rbx, rdx
0x1400291a3  mov     rsi, rcx
0x1400291a6  cmp     rdx, rax
0x1400291a9  jnz     loc_140029238
0x1400291af  cmp     r8d, [rdx+2ECh]
0x1400291b6  jnb     short loc_1400291BF
0x1400291b8  mov     ebp, 0C00000C3h
0x1400291bd  jmp     short loc_1400291D5
0x1400291bf  mov     rdx, [rcx+48h]
0x1400291c3  xor     ebp, ebp
0x1400291c5  mov     rcx, [rbx+2C8h]
0x1400291cc  call    Smb2ValidateNegotiateInfo
0x1400291d1  test    al, al
0x1400291d3  jnz     short loc_14002921A
0x1400291d5  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400291dc  lea     rax, WPP_GLOBAL_Control
0x1400291e3  mov     edi, 0Dh
0x1400291e8  cmp     rcx, rax
0x1400291eb  jz      short loc_140029210
0x1400291ed  mov     eax, [rcx+2Ch]
0x1400291f0  test    al, 1
0x1400291f2  jz      short loc_140029210
0x1400291f4  cmp     byte ptr [rcx+29h], 1
0x1400291f8  jb      short loc_140029210
0x1400291fa  mov     r9, [rsi+48h]
0x1400291fe  lea     r8, WPP_bbbb5ecce09d378367c344661863d2d2_Traceguids
0x140029205  mov     rcx, [rcx+18h]
0x140029209  mov     edx, edi
0x14002920b  call    WPP_SF_q
0x140029210  mov     rcx, rsi
0x140029213  call    Smb2ProcessNegotiateValidationFailure
0x140029218  jmp     short loc_14002921C
0x14002921a  xor     edi, edi
0x14002921c  mov     dword ptr [rsp+48h+arg_0], ebp
0x140029220  mov     rcx, rbx
0x140029223  mov     dword ptr [rsp+48h+arg_0+4], edi
0x140029227  mov     rdx, [rsp+48h+arg_0]
0x14002922c  call    cs:__imp_SmbCseUpdateBufferContextStatus
0x140029233  nop     dword ptr [rax+rax+00h]
0x140029238  xor     eax, eax
0x14002923a  add     rsp, 28h
0x14002923e  pop     rdi
0x14002923f  pop     rsi
0x140029240  pop     rbp
0x140029241  pop     rbx
0x140029242  retn
```
