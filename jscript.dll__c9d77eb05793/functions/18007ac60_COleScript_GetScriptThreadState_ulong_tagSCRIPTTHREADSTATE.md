# COleScript::GetScriptThreadState(ulong,tagSCRIPTTHREADSTATE *)

- ea: `0x18007ac60`
- end: `0x18007acce`
- name: `?GetScriptThreadState@COleScript@@UEAAJKPEAW4tagSCRIPTTHREADSTATE@@@Z`
- size: `110`
- prototype: `__int64 __fastcall(COleScript *__hidden this, unsigned int, enum tagSCRIPTTHREADSTATE *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18007ac60`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18007ac77`
- `KERNEL32!GetCurrentThreadId` at `0x18007ac77`

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
0x18007ac60  mov     [rsp+arg_0], rbx
0x18007ac65  push    rdi
0x18007ac66  sub     rsp, 20h
0x18007ac6a  mov     rdi, r8
0x18007ac6d  mov     eax, edx
0x18007ac6f  mov     rbx, rcx
0x18007ac72  cmp     edx, 0FFFFFFFFh
0x18007ac75  jnz     short loc_18007AC7F
0x18007ac77  call    cs:__imp_GetCurrentThreadId
0x18007ac7d  jmp     short loc_18007AC8A
0x18007ac7f  cmp     eax, 0FFFFFFFEh
0x18007ac82  jnz     short loc_18007AC8A
0x18007ac84  mov     eax, [rcx+104h]
0x18007ac8a  test    rdi, rdi
0x18007ac8d  jnz     short loc_18007AC96
0x18007ac8f  mov     eax, 80004003h
0x18007ac94  jmp     short loc_18007ACC3
0x18007ac96  mov     dword ptr [rdi], 0
0x18007ac9c  mov     ecx, [rbx+104h]
0x18007aca2  cmp     ecx, 0FFFFFFFFh
0x18007aca5  jnz     short loc_18007ACAE
0x18007aca7  mov     eax, 8000FFFFh
0x18007acac  jmp     short loc_18007ACC3
0x18007acae  cmp     eax, ecx
0x18007acb0  jz      short loc_18007ACB9
0x18007acb2  mov     eax, 80070057h
0x18007acb7  jmp     short loc_18007ACC3
0x18007acb9  mov     eax, [rbx+128h]
0x18007acbf  mov     [rdi], eax
0x18007acc1  xor     eax, eax
0x18007acc3  mov     rbx, [rsp+28h+arg_0]
0x18007acc8  add     rsp, 20h
0x18007accc  pop     rdi
0x18007accd  retn
```
