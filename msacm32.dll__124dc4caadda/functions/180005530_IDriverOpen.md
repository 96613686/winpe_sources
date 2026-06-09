# IDriverOpen

- ea: `0x180005530`
- end: `0x1800056f7`
- name: `IDriverOpen`
- size: `455`
- prototype: `__int64 __fastcall(__int64 *, __int64, int)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180002470`
- `0x180002e70`

## callees

- `0x180001e60`
- `0x1800040a0`
- `0x1800043d0`
- `0x180005530`
- `0x180005700`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800055c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800055c0`
- `api-ms-win-mm-misc-l1-1-0!OpenDriver` at `0x18000562d`
- `api-ms-win-mm-misc-l1-1-0!OpenDriver` at `0x18000562d`

## pseudocode

```c
__int64 __fastcall IDriverOpen(__int64 *a1, __int64 a2, int a3)
{
  int v5; // eax
  __int64 v6; // rax
  __int64 v7; // rdi
  DWORD CurrentThreadId; // eax
  const WCHAR *v9; // rcx
  const WCHAR *v10; // rdx
  int v11; // eax
  HDRVR v12; // rax
  __int64 result; // rax
  __int64 v14; // rax
  LPARAM lParam2[7]; // [rsp+20h] [rbp-38h] BYREF

  memset(lParam2, 0, 44);
  if ( !a1 )
    return 11;
  *a1 = 0;
  if ( !a2 )
    return 5;
  if ( a3 )
    return 10;
  if ( (*(_DWORD *)(a2 + 56) & 1) == 0 )
  {
    result = IDriverLoad(a2);
    if ( (_DWORD)result )
      return result;
  }
  v5 = *(_DWORD *)(a2 + 56);
  if ( (v5 & 0x10000000) != 0 )
    return 5;
  if ( v5 < 0 )
    return 3;
  v6 = NewHandle(64);
  v7 = v6;
  if ( !v6 )
    return 7;
  *(_DWORD *)v6 = 2;
  *(_QWORD *)(v6 + 12) = 0;
  *(_QWORD *)(v6 + 20) = a2;
  CurrentThreadId = GetCurrentThreadId();
  *(_DWORD *)(v7 + 36) = 0;
  v9 = (const WCHAR *)(a2 + 120);
  *(_QWORD *)(v7 + 28) = CurrentThreadId;
  *(_QWORD *)(v7 + 4) = *(_QWORD *)(a2 + 28);
  v10 = *(const WCHAR **)(a2 + 112);
  v11 = *(_DWORD *)(a2 + 416);
  lParam2[3] = (LPARAM)v10;
  *(_QWORD *)(a2 + 28) = v7;
  LODWORD(lParam2[0]) = 44;
  *(LPARAM *)((char *)lParam2 + 4) = 1667528033;
  *(LPARAM *)((char *)&lParam2[1] + 4) = 83886080;
  HIDWORD(lParam2[2]) = 0;
  lParam2[4] = a2 + 120;
  LODWORD(lParam2[5]) = v11;
  if ( *(_QWORD *)(a2 + 88) )
  {
    if ( (*(_DWORD *)(a2 + 52) & 0x40000000) != 0 )
    {
      v9 = *(const WCHAR **)(a2 + 408);
      v10 = 0;
    }
    v12 = OpenDriver(v9, v10, (LPARAM)lParam2);
    if ( v12 )
    {
      *(_QWORD *)(v7 + 40) = v12;
LABEL_13:
      *a1 = v7;
      return 0;
    }
    IDriverClose(v7, 0);
    result = HIDWORD(lParam2[2]);
    if ( !HIDWORD(lParam2[2]) )
      return 1;
  }
  else
  {
    v14 = ((__int64 (__fastcall *)(__int64, __int64, _QWORD, LPARAM *))IDriverMessageId)(a2, 3, 0, lParam2);
    if ( v14 )
    {
      *(_QWORD *)(v7 + 56) = v14;
      *(_QWORD *)(v7 + 48) = *(_QWORD *)(a2 + 96);
      goto LABEL_13;
    }
    IDriverClose(v7, 0);
    result = HIDWORD(lParam2[2]);
    if ( !HIDWORD(lParam2[2]) )
      return 1;
  }
  return result;
}

```

## disassembly

```asm
0x180005530  mov     [rsp+arg_10], rbx
0x180005535  push    rsi
0x180005536  sub     rsp, 50h
0x18000553a  xorps   xmm0, xmm0
0x18000553d  mov     rbx, rdx
0x180005540  mov     rsi, rcx
0x180005543  movups  [rsp+58h+var_28], xmm0
0x180005548  movups  [rsp+58h+var_28+0Ch], xmm0
0x18000554d  movups  xmmword ptr [rsp+58h+lParam2], xmm0
0x180005552  test    rcx, rcx
0x180005555  jz      loc_180005697
0x18000555b  mov     [rsp+58h+arg_0], rbp
0x180005560  xor     ebp, ebp
0x180005562  mov     [rcx], rbp
0x180005565  test    rdx, rdx
0x180005568  jz      loc_1800056ED
0x18000556e  test    r8d, r8d
0x180005571  jnz     loc_18000569E
0x180005577  mov     eax, [rdx+38h]
0x18000557a  test    al, 1
0x18000557c  jz      loc_1800056A5
0x180005582  mov     eax, [rbx+38h]
0x180005585  bt      eax, 1Ch
0x180005589  jb      loc_1800056ED
0x18000558f  test    eax, eax
0x180005591  js      loc_1800056B6
0x180005597  mov     ecx, 40h ; '@'
0x18000559c  mov     [rsp+58h+arg_8], rdi
0x1800055a1  call    NewHandle
0x1800055a6  mov     rdi, rax
0x1800055a9  test    rax, rax
0x1800055ac  jz      loc_1800056BD
0x1800055b2  mov     dword ptr [rax], 2
0x1800055b8  mov     [rax+0Ch], rbp
0x1800055bc  mov     [rax+14h], rbx
0x1800055c0  call    cs:__imp_GetCurrentThreadId
0x1800055c6  mov     [rdi+24h], ebp
0x1800055c9  lea     rcx, [rbx+78h]; szDriverName
0x1800055cd  mov     eax, eax
0x1800055cf  mov     [rdi+1Ch], rax
0x1800055d3  mov     rax, [rbx+1Ch]
0x1800055d7  mov     [rdi+4], rax
0x1800055db  mov     rdx, [rbx+70h]; szSectionName
0x1800055df  mov     eax, [rbx+1A0h]
0x1800055e5  mov     qword ptr [rsp+58h+var_28+8], rdx
0x1800055ea  mov     [rbx+1Ch], rdi
0x1800055ee  mov     dword ptr [rsp+58h+lParam2], 2Ch ; ','
0x1800055f6  mov     [rsp+58h+lParam2+4], 63647561h
0x1800055ff  mov     [rsp+58h+lParam2+0Ch], 5000000h
0x180005608  mov     dword ptr [rsp+58h+var_28+4], ebp
0x18000560c  mov     [rsp+58h+var_18], rcx
0x180005611  mov     [rsp+58h+var_10], eax
0x180005615  cmp     [rbx+58h], rbp
0x180005619  jz      short loc_180005656
0x18000561b  test    dword ptr [rbx+34h], 40000000h
0x180005622  lea     r8, [rsp+58h+lParam2]; lParam2
0x180005627  jnz     loc_1800056C7
0x18000562d  call    cs:__imp_OpenDriver
0x180005633  test    rax, rax
0x180005636  jz      short loc_18000567E
0x180005638  mov     [rdi+28h], rax
0x18000563c  mov     [rsi], rdi
0x18000563f  xor     eax, eax
0x180005641  mov     rdi, [rsp+58h+arg_8]
0x180005646  mov     rbp, [rsp+58h+arg_0]
0x18000564b  mov     rbx, [rsp+58h+arg_10]
0x180005650  add     rsp, 50h
0x180005654  pop     rsi
0x180005655  retn
0x180005656  lea     r9, [rsp+58h+lParam2]
0x18000565b  xor     r8d, r8d
0x18000565e  mov     edx, 3
0x180005663  mov     rcx, rbx
0x180005666  call    IDriverMessageId
0x18000566b  test    rax, rax
0x18000566e  jz      short loc_1800056D5
0x180005670  mov     [rdi+38h], rax
0x180005674  mov     rax, [rbx+60h]
0x180005678  mov     [rdi+30h], rax
0x18000567c  jmp     short loc_18000563C
0x18000567e  xor     edx, edx
0x180005680  mov     rcx, rdi
0x180005683  call    IDriverClose
0x180005688  mov     eax, dword ptr [rsp+58h+var_28+4]
0x18000568c  test    eax, eax
0x18000568e  jnz     short loc_180005641
0x180005690  mov     eax, 1
0x180005695  jmp     short loc_180005641
0x180005697  mov     eax, 0Bh
0x18000569c  jmp     short loc_18000564B
0x18000569e  mov     eax, 0Ah
0x1800056a3  jmp     short loc_180005646
0x1800056a5  mov     rcx, rbx
0x1800056a8  call    IDriverLoad
0x1800056ad  test    eax, eax
0x1800056af  jnz     short loc_180005646
0x1800056b1  jmp     loc_180005582
0x1800056b6  mov     eax, 3
0x1800056bb  jmp     short loc_180005646
0x1800056bd  mov     eax, 7
0x1800056c2  jmp     loc_180005641
0x1800056c7  mov     rcx, [rbx+198h]
0x1800056ce  xor     edx, edx
0x1800056d0  jmp     loc_18000562D
0x1800056d5  xor     edx, edx
0x1800056d7  mov     rcx, rdi
0x1800056da  call    IDriverClose
0x1800056df  mov     eax, dword ptr [rsp+58h+var_28+4]
0x1800056e3  test    eax, eax
0x1800056e5  jnz     loc_180005641
0x1800056eb  jmp     short loc_180005690
0x1800056ed  mov     eax, 5
0x1800056f2  jmp     loc_180005646
```
