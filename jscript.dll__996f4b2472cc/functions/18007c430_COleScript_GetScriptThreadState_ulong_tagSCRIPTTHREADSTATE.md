# COleScript::GetScriptThreadState(ulong,tagSCRIPTTHREADSTATE *)

- ea: `0x18007c430`
- end: `0x18007c4a5`
- name: `?GetScriptThreadState@COleScript@@UEAAJKPEAW4tagSCRIPTTHREADSTATE@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(COleScript *__hidden this, unsigned int, enum tagSCRIPTTHREADSTATE *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18007c430`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18007c447`
- `KERNEL32!GetCurrentThreadId` at `0x18007c447`

## pseudocode

```c
__int64 __fastcall COleScript::GetScriptThreadState(COleScript *this, DWORD a2, enum tagSCRIPTTHREADSTATE *a3)
{
  DWORD CurrentThreadId; // eax
  int v7; // ecx

  CurrentThreadId = a2;
  if ( a2 == -1 )
  {
    CurrentThreadId = GetCurrentThreadId();
  }
  else if ( a2 == -2 )
  {
    CurrentThreadId = *((_DWORD *)this + 65);
  }
  if ( !a3 )
    return 2147500035LL;
  *a3 = SCRIPTTHREADSTATE_NOTINSCRIPT;
  v7 = *((_DWORD *)this + 65);
  if ( v7 == -1 )
    return 2147549183LL;
  if ( CurrentThreadId != v7 )
    return 2147942487LL;
  *a3 = *((enum tagSCRIPTTHREADSTATE *)this + 74);
  return 0;
}

```

## disassembly

```asm
0x18007c430  mov     [rsp+arg_0], rbx
0x18007c435  push    rdi
0x18007c436  sub     rsp, 20h
0x18007c43a  mov     rdi, r8
0x18007c43d  mov     eax, edx
0x18007c43f  mov     rbx, rcx
0x18007c442  cmp     edx, 0FFFFFFFFh
0x18007c445  jnz     short loc_18007C455
0x18007c447  call    cs:__imp_GetCurrentThreadId
0x18007c44e  nop     dword ptr [rax+rax+00h]
0x18007c453  jmp     short loc_18007C460
0x18007c455  cmp     eax, 0FFFFFFFEh
0x18007c458  jnz     short loc_18007C460
0x18007c45a  mov     eax, [rcx+104h]
0x18007c460  test    rdi, rdi
0x18007c463  jnz     short loc_18007C46C
0x18007c465  mov     eax, 80004003h
0x18007c46a  jmp     short loc_18007C499
0x18007c46c  mov     dword ptr [rdi], 0
0x18007c472  mov     ecx, [rbx+104h]
0x18007c478  cmp     ecx, 0FFFFFFFFh
0x18007c47b  jnz     short loc_18007C484
0x18007c47d  mov     eax, 8000FFFFh
0x18007c482  jmp     short loc_18007C499
0x18007c484  cmp     eax, ecx
0x18007c486  jz      short loc_18007C48F
0x18007c488  mov     eax, 80070057h
0x18007c48d  jmp     short loc_18007C499
0x18007c48f  mov     eax, [rbx+128h]
0x18007c495  mov     [rdi], eax
0x18007c497  xor     eax, eax
0x18007c499  mov     rbx, [rsp+28h+arg_0]
0x18007c49e  add     rsp, 20h
0x18007c4a2  pop     rdi
0x18007c4a3  retn
```
