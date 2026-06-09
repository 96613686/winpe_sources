# sub_1800EFEA0

- ea: `0x1800efea0`
- end: `0x1800effcf`
- name: `sub_1800EFEA0`
- size: `303`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800efea0`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800efebb`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800efebb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800eff37`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800eff37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800efed7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eff7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800efed7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eff7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800effaf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800effaf`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1800eff17`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1800eff17`

## pseudocode

```c
signed int __fastcall sub_1800EFEA0(__int64 a1)
{
  HANDLE Event; // rax
  signed int result; // eax
  HANDLE *v4; // r14
  signed int v5; // ebx
  signed int LastError; // eax

  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  *(_QWORD *)(a1 - 8 + 168) = Event;
  if ( Event )
  {
    sub_18018C010();
    if ( QueueUserWorkItem(Function, (PVOID)(a1 - 8), 0x100u) )
    {
      v4 = (HANDLE *)(a1 + 160);
      if ( WaitForSingleObject(*(HANDLE *)(a1 + 160), 0x1388u) )
      {
        v5 = -2147418113;
        sub_18018C010();
        return v5;
      }
      v5 = *(_DWORD *)(a1 + 152);
      if ( v5 < 0 )
        sub_18018C010();
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      sub_18018C010();
      v4 = (HANDLE *)(a1 + 160);
    }
    CloseHandle(*v4);
    *v4 = 0;
    return v5;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800efea0  push    rbx
0x1800efea2  push    rsi
0x1800efea3  push    rdi
0x1800efea4  push    r14
0x1800efea6  sub     rsp, 28h
0x1800efeaa  xor     edx, edx; lpName
0x1800efeac  mov     rdi, rcx
0x1800efeaf  xor     ecx, ecx; lpEventAttributes
0x1800efeb1  mov     r9d, 1F0003h; dwDesiredAccess
0x1800efeb7  lea     r8d, [rdx+1]; dwFlags
0x1800efebb  call    cs:CreateEventExW
0x1800efec2  nop     dword ptr [rax+rax+00h]
0x1800efec7  lea     rsi, [rdi-8]
0x1800efecb  mov     [rsi+0A8h], rax
0x1800efed2  test    rax, rax
0x1800efed5  jnz     short loc_1800EFEF8
0x1800efed7  call    cs:GetLastError
0x1800efede  nop     dword ptr [rax+rax+00h]
0x1800efee3  test    eax, eax
0x1800efee5  jle     loc_1800EFFC4
0x1800efeeb  movzx   eax, ax
0x1800efeee  or      eax, 80070000h
0x1800efef3  jmp     loc_1800EFFC4
0x1800efef8  mov     rax, [rsi]
0x1800efefb  mov     rcx, rsi
0x1800efefe  mov     rax, [rax+8]
0x1800eff02  call    sub_18018C010
0x1800eff07  mov     r8d, 100h; Flags
0x1800eff0d  lea     rcx, Function; Function
0x1800eff14  mov     rdx, rsi; Context
0x1800eff17  call    cs:QueueUserWorkItem
0x1800eff1e  nop     dword ptr [rax+rax+00h]
0x1800eff23  cmp     eax, 1
0x1800eff26  jnz     short loc_1800EFF7B
0x1800eff28  lea     r14, [rdi+0A0h]
0x1800eff2f  mov     edx, 1388h; dwMilliseconds
0x1800eff34  mov     rcx, [r14]; hHandle
0x1800eff37  call    cs:WaitForSingleObject
0x1800eff3e  nop     dword ptr [rax+rax+00h]
0x1800eff43  test    eax, eax
0x1800eff45  jnz     short loc_1800EFF62
0x1800eff47  mov     ebx, [rdi+98h]
0x1800eff4d  test    ebx, ebx
0x1800eff4f  jns     short loc_1800EFFAC
0x1800eff51  mov     rax, [rsi]
0x1800eff54  mov     rcx, rsi
0x1800eff57  mov     rax, [rax+10h]
0x1800eff5b  call    sub_18018C010
0x1800eff60  jmp     short loc_1800EFFAC
0x1800eff62  mov     rax, [rdi]
0x1800eff65  mov     rcx, rdi
0x1800eff68  mov     ebx, 8000FFFFh
0x1800eff6d  mov     rax, [rax+98h]
0x1800eff74  call    sub_18018C010
0x1800eff79  jmp     short loc_1800EFFC2
0x1800eff7b  call    cs:GetLastError
0x1800eff82  nop     dword ptr [rax+rax+00h]
0x1800eff87  mov     ebx, eax
0x1800eff89  test    eax, eax
0x1800eff8b  jle     short loc_1800EFF96
0x1800eff8d  movzx   ebx, ax
0x1800eff90  or      ebx, 80070000h
0x1800eff96  mov     rcx, [rsi]
0x1800eff99  mov     rax, [rcx+10h]
0x1800eff9d  mov     rcx, rsi
0x1800effa0  call    sub_18018C010
0x1800effa5  lea     r14, [rdi+0A0h]
0x1800effac  mov     rcx, [r14]; hObject
0x1800effaf  call    cs:CloseHandle
0x1800effb6  nop     dword ptr [rax+rax+00h]
0x1800effbb  mov     qword ptr [r14], 0
0x1800effc2  mov     eax, ebx
0x1800effc4  add     rsp, 28h
0x1800effc8  pop     r14
0x1800effca  pop     rdi
0x1800effcb  pop     rsi
0x1800effcc  pop     rbx
0x1800effcd  retn
```
