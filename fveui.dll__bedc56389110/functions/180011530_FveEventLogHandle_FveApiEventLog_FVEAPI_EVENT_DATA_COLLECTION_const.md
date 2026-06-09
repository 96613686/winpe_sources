# FveEventLogHandle::FveApiEventLog(_FVEAPI_EVENT_DATA_COLLECTION const *)

- ea: `0x180011530`
- end: `0x180011615`
- name: `?FveApiEventLog@FveEventLogHandle@@SAJPEBU_FVEAPI_EVENT_DATA_COLLECTION@@@Z`
- size: `229`
- prototype: `__int64 __fastcall(const struct _FVEAPI_EVENT_DATA_COLLECTION *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800116f4`

## callees

- `0x180001bb0`
- `0x180002774`
- `0x180011530`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800115d9`
- `ntdll!EtwEventWrite` at `0x1800115d9`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall FveEventLogHandle::FveApiEventLog(const struct _FVEAPI_EVENT_DATA_COLLECTION *a1)
{
  unsigned int v2; // ebx
  char *v3; // r10
  char *v4; // r9
  __int64 v5; // r8
  int v6; // ecx
  __int64 v7; // rdx
  int v8; // eax
  __int64 v10; // [rsp+20h] [rbp-218h] BYREF
  _DWORD v11[126]; // [rsp+28h] [rbp-210h] BYREF

  v10 = 0;
  memset_0(v11, 0, sizeof(v11));
  if ( a1 )
  {
    v3 = (char *)a1 + 16;
    v2 = 0;
    v4 = (char *)*((_QWORD *)a1 + 2);
    v5 = 0;
    if ( v4 != (char *)a1 + 16 )
    {
      do
      {
        if ( (unsigned int)v5 >= 0x25 )
          break;
        if ( (unsigned int)v5 < 0x20 )
        {
          v6 = *((_DWORD *)v4 + 10);
          v7 = 2LL * (unsigned int)v5;
          *(_QWORD *)&v11[2 * v7 - 2] = *((_QWORD *)v4 + 4);
          v11[2 * v7] = v6;
          v11[2 * v7 + 1] = 0;
        }
        v4 = *(char **)v4;
        v5 = (unsigned int)(v5 + 1);
      }
      while ( v4 != v3 );
      if ( (unsigned int)v5 >= 0x20 && v4 != v3 )
        v2 = -2147024565;
    }
    v8 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, __int64 *))EtwEventWrite)(
           *(_QWORD *)a1,
           *((_QWORD *)a1 + 1),
           v5,
           &v10);
    if ( v8 )
    {
      if ( v8 > 0 )
        return (unsigned __int16)v8 | 0x80070000;
      else
        return (unsigned int)v8;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v2;
}

```

## disassembly

```asm
0x180011530  mov     [rsp+arg_8], rbx
0x180011535  push    rdi
0x180011536  sub     rsp, 230h
0x18001153d  mov     rax, cs:__security_cookie
0x180011544  xor     rax, rsp
0x180011547  mov     [rsp+238h+var_18], rax
0x18001154f  mov     rdi, rcx
0x180011552  mov     [rsp+238h+var_218], 0
0x18001155b  lea     rcx, [rsp+238h+var_210]; void *
0x180011560  xor     edx, edx; Val
0x180011562  mov     r8d, 1F8h; Size
0x180011568  call    memset_0
0x18001156d  test    rdi, rdi
0x180011570  jnz     short loc_180011579
0x180011572  mov     ebx, 80070057h
0x180011577  jmp     short loc_1800115F2
0x180011579  lea     r10, [rdi+10h]
0x18001157d  xor     ebx, ebx
0x18001157f  mov     r9, [r10]
0x180011582  xor     r8d, r8d
0x180011585  cmp     r9, r10
0x180011588  jz      short loc_1800115CD
0x18001158a  cmp     r8d, 25h ; '%'
0x18001158e  jnb     short loc_1800115BC
0x180011590  cmp     r8d, 20h ; ' '
0x180011594  jnb     short loc_1800115B1
0x180011596  mov     rax, [r9+20h]
0x18001159a  mov     ecx, [r9+28h]
0x18001159e  mov     edx, r8d
0x1800115a1  add     rdx, rdx
0x1800115a4  mov     [rsp+rdx*8+238h+var_218], rax
0x1800115a9  mov     [rsp+rdx*8+238h+var_210], ecx
0x1800115ad  mov     [rsp+rdx*8+238h+var_20C], ebx
0x1800115b1  mov     r9, [r9]
0x1800115b4  inc     r8d
0x1800115b7  cmp     r9, r10
0x1800115ba  jnz     short loc_18001158A
0x1800115bc  cmp     r8d, 20h ; ' '
0x1800115c0  jb      short loc_1800115CD
0x1800115c2  cmp     r9, r10
0x1800115c5  mov     eax, 8007014Bh
0x1800115ca  cmovnz  ebx, eax
0x1800115cd  mov     rdx, [rdi+8]
0x1800115d1  lea     r9, [rsp+238h+var_218]
0x1800115d6  mov     rcx, [rdi]
0x1800115d9  call    cs:__imp_EtwEventWrite
0x1800115df  test    eax, eax
0x1800115e1  jz      short loc_1800115F2
0x1800115e3  jg      short loc_1800115E9
0x1800115e5  mov     ebx, eax
0x1800115e7  jmp     short loc_1800115F2
0x1800115e9  movzx   ebx, ax
0x1800115ec  or      ebx, 80070000h
0x1800115f2  mov     eax, ebx
0x1800115f4  mov     rcx, [rsp+238h+var_18]
0x1800115fc  xor     rcx, rsp; StackCookie
0x1800115ff  call    __security_check_cookie
0x180011604  mov     rbx, [rsp+238h+arg_8]
0x18001160c  add     rsp, 230h
0x180011613  pop     rdi
0x180011614  retn
```
