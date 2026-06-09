# DeleteLocalManagementEnrollment(_GUID &)

- ea: `0x180006488`
- end: `0x18000662d`
- name: `?DeleteLocalManagementEnrollment@@YAJAEAU_GUID@@@Z`
- size: `421`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005d20`

## callees

- `0x180006488`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000656a`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000656a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006555`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006555`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006505`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006505`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800064e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800064e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800064f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800065f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800064f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800065f3`
- `dmEnrollEngine!EnrollEngineInitialize` at `0x1800064b7`
- `dmEnrollEngine!EnrollEngineInitialize` at `0x1800064b7`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DeleteLocalManagementEnrollment(struct _GUID *a1)
{
  signed int v2; // ebx
  __int64 v3; // rsi
  __int64 (__fastcall *v4)(__int64, struct _GUID *, HANDLE *); // r14
  DWORD LastError; // ebx
  int v6; // edi
  signed int v7; // eax
  HANDLE hObject; // [rsp+30h] [rbp-20h] BYREF
  __int64 v10; // [rsp+38h] [rbp-18h] BYREF
  struct _GUID v11; // [rsp+40h] [rbp-10h] BYREF
  int v12; // [rsp+88h] [rbp+38h] BYREF
  signed int v13; // [rsp+90h] [rbp+40h] BYREF
  int v14; // [rsp+98h] [rbp+48h] BYREF

  v10 = 0;
  hObject = 0;
  v2 = EnrollEngineInitialize(1, 0, &v10);
  if ( v2 >= 0 )
  {
    v3 = v10;
    v4 = *(__int64 (__fastcall **)(__int64, struct _GUID *, HANDLE *))(*(_QWORD *)v10 + 72LL);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      LastError = GetLastError();
      CloseHandle(hObject);
      SetLastError(LastError);
    }
    hObject = 0;
    v2 = v4(v3, a1, &hObject);
    if ( v2 >= 0 )
    {
      v6 = 0;
      while ( 1 )
      {
        v13 = 0;
        v12 = 14;
        v14 = 0;
        if ( WaitForSingleObject(hObject, 0x3E8u) == -1 )
          break;
        ResetEvent(hObject);
        v11 = *a1;
        v2 = (*(__int64 (__fastcall **)(__int64, struct _GUID *, int *, signed int *, int *))(*(_QWORD *)v10 + 88LL))(
               v10,
               &v11,
               &v12,
               &v13,
               &v14);
        if ( v2 < 0 )
          goto LABEL_15;
        if ( v12 == 5 )
        {
          v2 = v13;
          goto LABEL_15;
        }
        if ( ++v6 >= 30 )
        {
          v2 = -2147483638;
          if ( v6 == 30 )
            v2 = -2147467259;
          goto LABEL_15;
        }
      }
      v7 = GetLastError();
      v2 = v7;
      if ( v7 > 0 )
        v2 = (unsigned __int16)v7 | 0x80070000;
    }
  }
LABEL_15:
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 112LL))(v10);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180006488  mov     [rsp-28h+arg_0], rbx
0x18000648d  push    rbp
0x18000648e  push    rsi
0x18000648f  push    rdi
0x180006490  push    r14
0x180006492  push    r15
0x180006494  mov     rbp, rsp
0x180006497  sub     rsp, 50h
0x18000649b  mov     r15, rcx
0x18000649e  mov     [rbp+var_18], 0
0x1800064a6  mov     [rbp+hObject], 0
0x1800064ae  lea     r8, [rbp+var_18]
0x1800064b2  xor     edx, edx
0x1800064b4  lea     ecx, [rdx+1]
0x1800064b7  call    cs:__imp_EnrollEngineInitialize
0x1800064be  nop     dword ptr [rax+rax+00h]
0x1800064c3  mov     ebx, eax
0x1800064c5  test    eax, eax
0x1800064c7  js      loc_1800065E5
0x1800064cd  mov     rsi, [rbp+var_18]
0x1800064d1  mov     rax, [rsi]
0x1800064d4  mov     r14, [rax+48h]
0x1800064d8  mov     rdi, [rbp+hObject]
0x1800064dc  lea     rax, [rdi-1]
0x1800064e0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800064e4  ja      short loc_180006511
0x1800064e6  call    cs:__imp_GetLastError
0x1800064ed  nop     dword ptr [rax+rax+00h]
0x1800064f2  mov     ebx, eax
0x1800064f4  mov     rcx, rdi; hObject
0x1800064f7  call    cs:__imp_CloseHandle
0x1800064fe  nop     dword ptr [rax+rax+00h]
0x180006503  mov     ecx, ebx; dwErrCode
0x180006505  call    cs:__imp_SetLastError
0x18000650c  nop     dword ptr [rax+rax+00h]
0x180006511  mov     [rbp+hObject], 0
0x180006519  lea     r8, [rbp+hObject]
0x18000651d  mov     rdx, r15
0x180006520  mov     rcx, rsi
0x180006523  mov     rax, r14
0x180006526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000652b  mov     ebx, eax
0x18000652d  test    eax, eax
0x18000652f  js      loc_1800065E5
0x180006535  xor     edi, edi
0x180006537  mov     [rbp+arg_10], 0
0x18000653e  mov     [rbp+arg_8], 0Eh
0x180006545  mov     [rbp+arg_18], 0
0x18000654c  mov     edx, 3E8h; dwMilliseconds
0x180006551  mov     rcx, [rbp+hObject]; hHandle
0x180006555  call    cs:__imp_WaitForSingleObject
0x18000655c  nop     dword ptr [rax+rax+00h]
0x180006561  cmp     eax, 0FFFFFFFFh
0x180006564  jz      short loc_1800065CA
0x180006566  mov     rcx, [rbp+hObject]; hEvent
0x18000656a  call    cs:__imp_ResetEvent
0x180006571  nop     dword ptr [rax+rax+00h]
0x180006576  mov     rcx, [rbp+var_18]
0x18000657a  movups  xmm0, xmmword ptr [r15]
0x18000657e  movdqu  [rbp+var_10], xmm0
0x180006583  mov     rax, [rcx]
0x180006586  lea     rdx, [rbp+arg_18]
0x18000658a  mov     [rsp+50h+var_30], rdx
0x18000658f  lea     r9, [rbp+arg_10]
0x180006593  lea     r8, [rbp+arg_8]
0x180006597  lea     rdx, [rbp+var_10]
0x18000659b  mov     rax, [rax+58h]
0x18000659f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065a4  mov     ebx, eax
0x1800065a6  test    eax, eax
0x1800065a8  js      short loc_1800065E5
0x1800065aa  cmp     [rbp+arg_8], 5
0x1800065ae  jz      short loc_1800065C5
0x1800065b0  inc     edi
0x1800065b2  cmp     edi, 1Eh
0x1800065b5  jl      short loc_180006537
0x1800065b7  mov     ebx, 8000000Ah
0x1800065bc  jnz     short loc_1800065E5
0x1800065be  mov     ebx, 80004005h
0x1800065c3  jmp     short loc_1800065E5
0x1800065c5  mov     ebx, [rbp+arg_10]
0x1800065c8  jmp     short loc_1800065E5
0x1800065ca  call    cs:__imp_GetLastError
0x1800065d1  nop     dword ptr [rax+rax+00h]
0x1800065d6  mov     ebx, eax
0x1800065d8  test    eax, eax
0x1800065da  jle     short loc_1800065E5
0x1800065dc  movzx   ebx, ax
0x1800065df  or      ebx, 80070000h
0x1800065e5  mov     rcx, [rbp+hObject]; hObject
0x1800065e9  lea     rax, [rcx-1]
0x1800065ed  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800065f1  ja      short loc_180006600
0x1800065f3  call    cs:__imp_CloseHandle
0x1800065fa  nop     dword ptr [rax+rax+00h]
0x1800065ff  nop
0x180006600  mov     rcx, [rbp+var_18]
0x180006604  test    rcx, rcx
0x180006607  jz      short loc_180006616
0x180006609  mov     rax, [rcx]
0x18000660c  mov     rax, [rax+70h]
0x180006610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006615  nop
0x180006616  mov     eax, ebx
0x180006618  mov     rbx, [rsp+50h+arg_0]
0x180006620  add     rsp, 50h
0x180006624  pop     r15
0x180006626  pop     r14
0x180006628  pop     rdi
0x180006629  pop     rsi
0x18000662a  pop     rbp
0x18000662b  retn
```
