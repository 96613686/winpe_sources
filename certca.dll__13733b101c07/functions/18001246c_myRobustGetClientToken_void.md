# myRobustGetClientToken(void * *)

- ea: `0x18001246c`
- end: `0x180012555`
- name: `?myRobustGetClientToken@@YAJPEAPEAX@Z`
- size: `233`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180031ddc`
- `0x1800370fc`

## callees

- `0x180008400`
- `0x18000fb00`
- `0x180012450`
- `0x18001246c`
- `0x18002a470`
- `0x18002cddc`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800124f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012542`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800124f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012542`

## pseudocode

```c
__int64 __fastcall myRobustGetClientToken(void **a1)
{
  unsigned int v2; // ebx
  unsigned int v3; // ecx
  int v4; // edx
  WINBOOL IsMember; // [rsp+30h] [rbp+10h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp+18h] BYREF

  IsMember = 0;
  hObject = 0;
  if ( !a1 )
  {
    v2 = -2147024809;
    v3 = 72876838;
    v4 = -2147024809;
LABEL_3:
    CSPrintErrorLineFile(v3, v4);
    goto LABEL_14;
  }
  if ( !CertTypeRetrieveClientToken(&hObject) )
  {
    v2 = myHLastError();
    v4 = v2;
    v3 = 73270054;
    goto LABEL_3;
  }
  if ( !(unsigned int)myIsLocalSystem(hObject, &IsMember) )
  {
    v2 = myHLastError();
    v4 = v2;
    v3 = 73728806;
    goto LABEL_3;
  }
  if ( IsMember )
  {
    if ( hObject )
    {
      CloseHandle(hObject);
      hObject = 0;
    }
    if ( !(unsigned int)myNetLogonUser(0, 0, 0, &hObject) )
    {
      v2 = myHLastError();
      v4 = v2;
      v3 = 74646310;
      goto LABEL_3;
    }
  }
  *a1 = hObject;
  v2 = 0;
  hObject = 0;
LABEL_14:
  if ( hObject )
    CloseHandle(hObject);
  return v2;
}

```

## disassembly

```asm
0x18001246c  mov     [rsp-8+arg_10], rbx
0x180012471  push    rbp
0x180012472  mov     rbp, rsp
0x180012475  sub     rsp, 20h
0x180012479  mov     [rbp+IsMember], 0
0x180012480  mov     rbx, rcx
0x180012483  mov     [rbp+hObject], 0
0x18001248b  test    rcx, rcx
0x18001248e  jnz     short loc_1800124A6
0x180012490  mov     ebx, 80070057h
0x180012495  mov     ecx, 4580326h; unsigned int
0x18001249a  mov     edx, ebx; int
0x18001249c  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800124a1  jmp     loc_180012539
0x1800124a6  lea     rcx, [rbp+hObject]; void **
0x1800124aa  call    ?CertTypeRetrieveClientToken@@YAHPEAPEAX@Z; CertTypeRetrieveClientToken(void * *)
0x1800124af  test    eax, eax
0x1800124b1  jnz     short loc_1800124C3
0x1800124b3  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x1800124b8  mov     ebx, eax
0x1800124ba  mov     edx, eax
0x1800124bc  mov     ecx, 45E0326h
0x1800124c1  jmp     short loc_18001249C
0x1800124c3  mov     rcx, [rbp+hObject]; TokenHandle
0x1800124c7  lea     rdx, [rbp+IsMember]; IsMember
0x1800124cb  call    ?myIsLocalSystem@@YAHPEAXPEAH@Z; myIsLocalSystem(void *,int *)
0x1800124d0  test    eax, eax
0x1800124d2  jnz     short loc_1800124E4
0x1800124d4  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x1800124d9  mov     ebx, eax
0x1800124db  mov     edx, eax
0x1800124dd  mov     ecx, 4650326h
0x1800124e2  jmp     short loc_18001249C
0x1800124e4  cmp     [rbp+IsMember], 0
0x1800124e8  jz      short loc_180012528
0x1800124ea  mov     rcx, [rbp+hObject]; hObject
0x1800124ee  test    rcx, rcx
0x1800124f1  jz      short loc_180012501
0x1800124f3  call    cs:__imp_CloseHandle
0x1800124f9  mov     [rbp+hObject], 0
0x180012501  lea     r9, [rbp+hObject]
0x180012505  xor     r8d, r8d; LPCWSTR
0x180012508  xor     edx, edx; LPCWSTR
0x18001250a  xor     ecx, ecx; lpString
0x18001250c  call    myNetLogonUser
0x180012511  test    eax, eax
0x180012513  jnz     short loc_180012528
0x180012515  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001251a  mov     ebx, eax
0x18001251c  mov     edx, eax
0x18001251e  mov     ecx, 4730326h
0x180012523  jmp     loc_18001249C
0x180012528  mov     rax, [rbp+hObject]
0x18001252c  mov     [rbx], rax
0x18001252f  xor     ebx, ebx
0x180012531  mov     [rbp+hObject], 0
0x180012539  mov     rcx, [rbp+hObject]; hObject
0x18001253d  test    rcx, rcx
0x180012540  jz      short loc_180012548
0x180012542  call    cs:__imp_CloseHandle
0x180012548  mov     eax, ebx
0x18001254a  mov     rbx, [rsp+20h+arg_10]
0x18001254f  add     rsp, 20h
0x180012553  pop     rbp
0x180012554  retn
```
