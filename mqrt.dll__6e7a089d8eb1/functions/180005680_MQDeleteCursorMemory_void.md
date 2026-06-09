# MQDeleteCursorMemory(void *)

- ea: `0x180005680`
- end: `0x1800056e1`
- name: `?MQDeleteCursorMemory@@YAJPEAX@Z`
- size: `97`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x1800027f4`
- `0x180005680`
- `0x180013c74`
- `0x180014458`

## pseudocode

```c
__int64 __fastcall MQDeleteCursorMemory(void *a1)
{
  int v2; // eax
  unsigned int v3; // ebx

  v2 = RtpOneTimeThreadInit();
  v3 = v2;
  if ( v2 >= 0 )
    operator delete(a1);
  else
    LogMsgHR(v2, (wchar_t *)L"rt/cursor", 0x450u);
  return v3;
}

```

## disassembly

```asm
0x180005680  mov     [rsp+arg_0], rbx
0x180005685  push    rdi
0x180005686  sub     rsp, 20h
0x18000568a  mov     rdi, rcx
0x18000568d  call    ?RtpOneTimeThreadInit@@YAJXZ; RtpOneTimeThreadInit(void)
0x180005692  mov     ebx, eax
0x180005694  test    eax, eax
0x180005696  jns     short loc_1800056B0
0x180005698  mov     r8d, 450h; unsigned __int16
0x18000569e  lea     rdx, aRtCursor; "rt/cursor"
0x1800056a5  mov     ecx, eax; int
0x1800056a7  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800056ac  mov     eax, ebx
0x1800056ae  jmp     short loc_1800056D6
0x1800056b0  mov     rcx, rdi; void *
0x1800056b3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800056b8  jmp     short loc_1800056AC
0x1800056ba  mov     r8d, 3Ch ; '<'; unsigned __int16
0x1800056c0  lea     rdx, aRtCursor; "rt/cursor"
0x1800056c7  mov     ecx, 0C00E0007h; int
0x1800056cc  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800056d1  mov     eax, 0C00E0007h
0x1800056d6  mov     rbx, [rsp+28h+arg_0]
0x1800056db  add     rsp, 20h
0x1800056df  pop     rdi
0x1800056e0  retn
```
