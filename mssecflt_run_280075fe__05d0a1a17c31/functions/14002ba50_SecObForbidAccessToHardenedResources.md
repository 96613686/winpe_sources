# SecObForbidAccessToHardenedResources

- ea: `0x14002ba50`
- end: `0x14002bc12`
- name: `SecObForbidAccessToHardenedResources`
- size: `450`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: ``

## callers

- `0x14002c2e0`

## callees

- `0x140006754`
- `0x140006b6c`
- `0x1400088e4`
- `0x1400088ec`
- `0x1400088f4`
- `0x1400088fc`
- `0x140011650`
- `0x14002ba50`
- `0x14002c378`
- `0x14003a830`
- `0x14003a83c`
- `0x14003b5cc`
- `0x14003b5d4`
- `0x140040704`
- `0x1400428e0`
- `0x1400428ec`
- `0x1400428f8`
- `0x140042900`
- `0x140042908`

## import_xrefs

- `ntoskrnl!PsGetThreadProcess` at `0x14002bab7`
- `ntoskrnl!PsGetThreadProcess` at `0x14002bab7`
- `ntoskrnl!PsThreadType` at `0x14002ba9d`
- `ntoskrnl!IoGetCurrentProcess` at `0x14002ba78`
- `ntoskrnl!IoGetCurrentProcess` at `0x14002ba78`

## pseudocode

```c
__int64 __fastcall SecObForbidAccessToHardenedResources(unsigned int *a1)
{
  struct _KTHREAD *v2; // rbp
  __int64 result; // rax
  unsigned int v4; // edx
  __int64 v5; // rsi
  __int64 v6; // rbx
  unsigned int *v7; // rdi
  unsigned int v8; // ebx
  PSLIST_ENTRY ListEntry; // [rsp+20h] [rbp-28h] BYREF
  PSLIST_ENTRY v10; // [rsp+28h] [rbp-20h] BYREF

  v2 = 0;
  result = (__int64)IoGetCurrentProcess();
  v4 = a1[1];
  v5 = result;
  v10 = 0;
  ListEntry = 0;
  if ( (v4 & 1) == 0 )
  {
    v6 = *((_QWORD *)a1 + 1);
    if ( *((POBJECT_TYPE **)a1 + 2) == PsThreadType )
    {
      v2 = (struct _KTHREAD *)*((_QWORD *)a1 + 1);
      result = (__int64)PsGetThreadProcess(v2);
      v6 = result;
    }
    if ( v5 != v6 )
    {
      if ( (dword_140020004 & 4) == 0
        || !(unsigned __int8)KclIsProcessWindowsProtectedLightOrAbove(-1)
        || (int)SecGetProcessContextByObject(v5, &v10) < 0
        || (result = (__int64)v10, (HIDWORD(v10[38].Next) & 0x20) == 0) )
      {
        result = SecGetProcessContextByObject(v6, &ListEntry);
        if ( (int)result >= 0 )
        {
          result = SecObShouldTargetProcessBeHardened(ListEntry);
          if ( (_BYTE)result )
          {
            result = *a1;
            if ( (_DWORD)result == 1 || (_DWORD)result == 2 )
            {
              v7 = (unsigned int *)*((_QWORD *)a1 + 4);
              v8 = *v7;
              if ( v2 )
              {
                if ( (unsigned __int8)SecIsCriticalThreadTerminationProtectionEnabled() )
                  v8 = SecRemoveTerminateProcessAccess(v8);
                if ( (unsigned __int8)SecIsCriticalThreadSuspendProtectionEnabled() )
                  v8 = SecRemoveSuspendThreadAccess(v8);
                result = SecIsCriticalThreadStrictProtectionEnabled();
                if ( (_BYTE)result )
                {
                  result = SecRemoveStrictThreadAccess(v8);
                  v8 = result;
                }
                if ( *v7 != v8 )
                {
                  *v7 = v8;
                  result = SecIncrementObCallbackBlockThreadAccessCount();
                }
              }
              else
              {
                if ( (unsigned __int8)SecIsCriticalProcessTerminationProtectionEnabled() )
                  v8 = SecRemoveTerminateProcessAccess(v8);
                if ( (unsigned __int8)SecIsCriticalProcessSuspendProtectionEnabled() )
                  v8 = SecRemoveSuspendProcessAccess(v8);
                result = SecIsCriticalProcessStrictProtectionEnabled();
                if ( (_BYTE)result )
                {
                  result = SecRemoveStrictProcessAccess(v8);
                  v8 = result;
                }
                if ( *v7 != v8 )
                {
                  *v7 = v8;
                  result = SecIncrementObCallbackBlockProcessAccessCount();
                }
              }
            }
          }
        }
      }
    }
    if ( ListEntry )
      result = SecReleaseProcessContext(ListEntry);
    if ( v10 )
      return SecReleaseProcessContext(v10);
  }
  return result;
}

```

## disassembly

```asm
0x14002ba50  mov     [rsp+arg_8], rbx
0x14002ba55  mov     [rsp+arg_10], rbp
0x14002ba5a  mov     [rsp+arg_18], rsi
0x14002ba5f  push    rdi
0x14002ba60  sub     rsp, 40h
0x14002ba64  mov     rax, cs:__security_cookie
0x14002ba6b  xor     rax, rsp
0x14002ba6e  mov     [rsp+48h+var_18], rax
0x14002ba73  mov     rdi, rcx
0x14002ba76  xor     ebp, ebp
0x14002ba78  call    cs:__imp_IoGetCurrentProcess
0x14002ba7f  nop     dword ptr [rax+rax+00h]
0x14002ba84  mov     edx, [rdi+4]
0x14002ba87  mov     rsi, rax
0x14002ba8a  mov     [rsp+48h+var_20], rbp
0x14002ba8f  mov     [rsp+48h+ListEntry], rbp
0x14002ba94  test    dl, 1
0x14002ba97  jnz     loc_14002BBEF
0x14002ba9d  mov     rcx, cs:__imp_PsThreadType
0x14002baa4  mov     rbx, [rdi+8]
0x14002baa8  mov     rdx, [rcx]
0x14002baab  cmp     [rdi+10h], rdx
0x14002baaf  jnz     short loc_14002BAC6
0x14002bab1  mov     rcx, rbx; Thread
0x14002bab4  mov     rbp, rbx
0x14002bab7  call    cs:__imp_PsGetThreadProcess
0x14002babe  nop     dword ptr [rax+rax+00h]
0x14002bac3  mov     rbx, rax
0x14002bac6  cmp     rsi, rbx
0x14002bac9  jz      loc_14002BBD1
0x14002bacf  mov     eax, cs:dword_140020004
0x14002bad5  test    al, 4
0x14002bad7  jz      short loc_14002BB0B
0x14002bad9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14002badd  call    KclIsProcessWindowsProtectedLightOrAbove
0x14002bae2  test    al, al
0x14002bae4  jz      short loc_14002BB0B
0x14002bae6  lea     rdx, [rsp+48h+var_20]
0x14002baeb  mov     rcx, rsi
0x14002baee  call    SecGetProcessContextByObject
0x14002baf3  test    eax, eax
0x14002baf5  js      short loc_14002BB0B
0x14002baf7  mov     rax, [rsp+48h+var_20]
0x14002bafc  mov     ecx, [rax+264h]
0x14002bb02  test    cl, 20h
0x14002bb05  jnz     loc_14002BBD1
0x14002bb0b  lea     rdx, [rsp+48h+ListEntry]
0x14002bb10  mov     rcx, rbx
0x14002bb13  call    SecGetProcessContextByObject
0x14002bb18  test    eax, eax
0x14002bb1a  js      loc_14002BBD1
0x14002bb20  mov     rcx, [rsp+48h+ListEntry]
0x14002bb25  call    SecObShouldTargetProcessBeHardened
0x14002bb2a  test    al, al
0x14002bb2c  jz      loc_14002BBD1
0x14002bb32  mov     eax, [rdi]
0x14002bb34  cmp     eax, 1
0x14002bb37  jz      short loc_14002BB42
0x14002bb39  cmp     eax, 2
0x14002bb3c  jnz     loc_14002BBD1
0x14002bb42  mov     rdi, [rdi+20h]
0x14002bb46  mov     ebx, [rdi]
0x14002bb48  test    rbp, rbp
0x14002bb4b  jz      short loc_14002BB90
0x14002bb4d  call    SecIsCriticalThreadTerminationProtectionEnabled
0x14002bb52  test    al, al
0x14002bb54  jz      short loc_14002BB5F
0x14002bb56  mov     ecx, ebx
0x14002bb58  call    SecRemoveTerminateProcessAccess
0x14002bb5d  mov     ebx, eax
0x14002bb5f  call    SecIsCriticalThreadSuspendProtectionEnabled
0x14002bb64  test    al, al
0x14002bb66  jz      short loc_14002BB71
0x14002bb68  mov     ecx, ebx
0x14002bb6a  call    SecRemoveSuspendThreadAccess
0x14002bb6f  mov     ebx, eax
0x14002bb71  call    SecIsCriticalThreadStrictProtectionEnabled
0x14002bb76  test    al, al
0x14002bb78  jz      short loc_14002BB83
0x14002bb7a  mov     ecx, ebx
0x14002bb7c  call    SecRemoveStrictThreadAccess
0x14002bb81  mov     ebx, eax
0x14002bb83  cmp     [rdi], ebx
0x14002bb85  jz      short loc_14002BBD1
0x14002bb87  mov     [rdi], ebx
0x14002bb89  call    SecIncrementObCallbackBlockThreadAccessCount
0x14002bb8e  jmp     short loc_14002BBD1
0x14002bb90  call    SecIsCriticalProcessTerminationProtectionEnabled
0x14002bb95  test    al, al
0x14002bb97  jz      short loc_14002BBA2
0x14002bb99  mov     ecx, ebx
0x14002bb9b  call    SecRemoveTerminateProcessAccess
0x14002bba0  mov     ebx, eax
0x14002bba2  call    SecIsCriticalProcessSuspendProtectionEnabled
0x14002bba7  test    al, al
0x14002bba9  jz      short loc_14002BBB4
0x14002bbab  mov     ecx, ebx
0x14002bbad  call    SecRemoveSuspendProcessAccess
0x14002bbb2  mov     ebx, eax
0x14002bbb4  call    SecIsCriticalProcessStrictProtectionEnabled
0x14002bbb9  test    al, al
0x14002bbbb  jz      short loc_14002BBC6
0x14002bbbd  mov     ecx, ebx
0x14002bbbf  call    SecRemoveStrictProcessAccess
0x14002bbc4  mov     ebx, eax
0x14002bbc6  cmp     [rdi], ebx
0x14002bbc8  jz      short loc_14002BBD1
0x14002bbca  mov     [rdi], ebx
0x14002bbcc  call    SecIncrementObCallbackBlockProcessAccessCount
0x14002bbd1  mov     rcx, [rsp+48h+ListEntry]; ListEntry
0x14002bbd6  test    rcx, rcx
0x14002bbd9  jz      short loc_14002BBE0
0x14002bbdb  call    SecReleaseProcessContext
0x14002bbe0  mov     rcx, [rsp+48h+var_20]; ListEntry
0x14002bbe5  test    rcx, rcx
0x14002bbe8  jz      short loc_14002BBEF
0x14002bbea  call    SecReleaseProcessContext
0x14002bbef  mov     rcx, [rsp+48h+var_18]
0x14002bbf4  xor     rcx, rsp; StackCookie
0x14002bbf7  call    __security_check_cookie
0x14002bbfc  mov     rbx, [rsp+48h+arg_8]
0x14002bc01  mov     rbp, [rsp+48h+arg_10]
0x14002bc06  mov     rsi, [rsp+48h+arg_18]
0x14002bc0b  add     rsp, 40h
0x14002bc0f  pop     rdi
0x14002bc10  retn
```
