# SSI_ELEMENT_LIST::Initialize(SSI_FILE *)

- ea: `0x180002dc0`
- end: `0x180003000`
- name: `?Initialize@SSI_ELEMENT_LIST@@AEAAJPEAVSSI_FILE@@@Z`
- size: `576`
- prototype: `signed int __fastcall(SSI_ELEMENT_LIST *this, struct SSI_FILE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180002978`

## callees

- `0x180002c10`
- `0x180002cb0`
- `0x180002dc0`
- `0x180003008`
- `0x180005756`
- `0x180005780`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002fbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002fbf`

## pseudocode

```c
signed int __fastcall SSI_ELEMENT_LIST::Initialize(SSI_ELEMENT_LIST *this, struct SSI_FILE *a2)
{
  signed int result; // eax
  __int64 v5; // rcx
  char *v6; // r14
  char *v7; // rbx
  char *v8; // r15
  char *v9; // rdi
  char *i; // rcx
  const char *v11; // rsi
  char *v12; // [rsp+30h] [rbp-D0h] BYREF
  int v13; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v14; // [rsp+3Ch] [rbp-C4h] BYREF
  unsigned int v15; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v16; // [rsp+48h] [rbp-B8h] BYREF
  char v17[2064]; // [rsp+50h] [rbp-B0h] BYREF

  if ( ((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)a2 + 2) + 56LL))(*((_QWORD *)a2 + 2)) & 0x10) != 0 )
    return -2147024809;
  if ( !*((_QWORD *)a2 + 3) && !(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)a2 + 2) + 72LL))(*((_QWORD *)a2 + 2)) )
    return 0;
  v5 = *((_QWORD *)a2 + 2);
  v16 = 0;
  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v5 + 64LL))(v5, &v16);
  if ( HIDWORD(v16) )
    return -2147024846;
  v6 = (char *)*((_QWORD *)a2 + 3);
  if ( !v6 )
    v6 = (char *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)a2 + 2) + 72LL))(*((_QWORD *)a2 + 2));
  v7 = v6;
  v12 = v6;
  v8 = &v6[(unsigned int)v16];
  v9 = v6;
  for ( i = v6; ; i = v7 )
  {
    if ( i >= v8 )
    {
      v11 = i;
    }
    else
    {
      do
      {
        v11 = i;
        if ( *v7 == 60 )
          break;
        v7 = i + 1;
        v12 = v7;
        ++i;
        v11 = v7;
      }
      while ( v7 < v8 );
    }
    if ( v11 + 4 >= v8 )
      break;
    if ( *++v7 != 37 && strncmp_0(v11, "<!--", 4u) )
      goto LABEL_21;
    v15 = 0;
    v14 = 0;
    v13 = 0;
    if ( !(unsigned int)SSI_ELEMENT_LIST::ParseSSITag(
                          &v12,
                          v8,
                          &v13,
                          (enum SSI_COMMANDS *)&v15,
                          (enum SSI_TAGS *)&v14,
                          v17) )
    {
      v7 = v12;
      break;
    }
    if ( !v13 )
    {
      v7 = v12 + 1;
LABEL_21:
      v12 = v7;
      continue;
    }
    *((_DWORD *)this + 86) = 1;
    if ( v9 != v11 && !(unsigned int)SSI_ELEMENT_LIST::AppendByteRange(this, (int)v9 - (int)v6, (int)v11 - (int)v9) )
      goto LABEL_31;
    if ( !(unsigned int)SSI_ELEMENT_LIST::AppendCommand(this, v15, v14, v17) )
      return -2147467259;
    v7 = v12;
    v9 = v12;
  }
  if ( v7 > v9 && !(unsigned int)SSI_ELEMENT_LIST::AppendByteRange(this, (int)v9 - (int)v6, (int)v7 - (int)v9) )
  {
LABEL_31:
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  return 0;
}

```

## disassembly

```asm
0x180002dc0  mov     [rsp-8+arg_10], rbx
0x180002dc5  mov     [rsp-8+arg_18], rsi
0x180002dca  push    rbp
0x180002dcb  push    rdi
0x180002dcc  push    r13
0x180002dce  push    r14
0x180002dd0  push    r15
0x180002dd2  lea     rbp, [rsp-770h]
0x180002dda  sub     rsp, 870h
0x180002de1  mov     rax, cs:__security_cookie
0x180002de8  xor     rax, rsp
0x180002deb  mov     [rbp+790h+var_30], rax
0x180002df2  mov     r13, rcx
0x180002df5  mov     rbx, rdx
0x180002df8  mov     rcx, [rdx+10h]
0x180002dfc  mov     rax, [rcx]
0x180002dff  mov     rax, [rax+38h]
0x180002e03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e08  test    al, 10h
0x180002e0a  jz      short loc_180002E16
0x180002e0c  mov     eax, 80070057h
0x180002e11  jmp     loc_180002FD5
0x180002e16  cmp     qword ptr [rbx+18h], 0
0x180002e1b  jnz     short loc_180002E36
0x180002e1d  mov     rcx, [rbx+10h]
0x180002e21  mov     rax, [rcx]
0x180002e24  mov     rax, [rax+48h]
0x180002e28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e2d  test    rax, rax
0x180002e30  jz      loc_180002FD3
0x180002e36  mov     rcx, [rbx+10h]
0x180002e3a  lea     rdx, [rsp+890h+var_848]
0x180002e3f  mov     [rsp+890h+var_848], 0
0x180002e48  mov     rax, [rcx]
0x180002e4b  mov     rax, [rax+40h]
0x180002e4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e54  cmp     dword ptr [rsp+890h+var_848+4], 0
0x180002e59  jz      short loc_180002E65
0x180002e5b  mov     eax, 80070032h
0x180002e60  jmp     loc_180002FD5
0x180002e65  mov     r14, [rbx+18h]
0x180002e69  test    r14, r14
0x180002e6c  jnz     short loc_180002E81
0x180002e6e  mov     rcx, [rbx+10h]
0x180002e72  mov     rax, [rcx]
0x180002e75  mov     rax, [rax+48h]
0x180002e79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e7e  mov     r14, rax
0x180002e81  mov     r15d, dword ptr [rsp+890h+var_848]
0x180002e86  mov     rbx, r14
0x180002e89  mov     [rsp+890h+var_860], rbx
0x180002e8e  add     r15, r14
0x180002e91  mov     rdi, r14
0x180002e94  mov     rcx, r14
0x180002e97  cmp     rcx, r15
0x180002e9a  jnb     short loc_180002EBA
0x180002e9c  cmp     byte ptr [rbx], 3Ch ; '<'
0x180002e9f  mov     rsi, rcx
0x180002ea2  jz      short loc_180002EBD
0x180002ea4  lea     rbx, [rcx+1]
0x180002ea8  mov     [rsp+890h+var_860], rbx
0x180002ead  mov     rcx, rbx
0x180002eb0  mov     rsi, rbx
0x180002eb3  cmp     rbx, r15
0x180002eb6  jb      short loc_180002E9C
0x180002eb8  jmp     short loc_180002EBD
0x180002eba  mov     rsi, rcx
0x180002ebd  lea     rax, [rsi+4]
0x180002ec1  cmp     rax, r15
0x180002ec4  jnb     loc_180002FA4
0x180002eca  inc     rbx
0x180002ecd  cmp     byte ptr [rbx], 25h ; '%'
0x180002ed0  jz      short loc_180002EEB
0x180002ed2  mov     r8d, 4; MaxCount
0x180002ed8  lea     rdx, Str2; "<!--"
0x180002edf  mov     rcx, rsi; Str1
0x180002ee2  call    strncmp_0
0x180002ee7  test    eax, eax
0x180002ee9  jnz     short loc_180002F41
0x180002eeb  lea     rax, [rsp+890h+var_840]
0x180002ef0  mov     [rsp+890h+var_850], 0
0x180002ef8  mov     [rsp+890h+var_868], rax; char *
0x180002efd  lea     r9, [rsp+890h+var_850]; enum SSI_COMMANDS *
0x180002f02  lea     rax, [rsp+890h+var_854]
0x180002f07  mov     [rsp+890h+var_854], 0
0x180002f0f  lea     r8, [rsp+890h+var_858]; int *
0x180002f14  mov     [rsp+890h+var_870], rax; enum SSI_TAGS *
0x180002f19  mov     rdx, r15; char *
0x180002f1c  mov     [rsp+890h+var_858], 0
0x180002f24  lea     rcx, [rsp+890h+var_860]; char **
0x180002f29  call    ?ParseSSITag@SSI_ELEMENT_LIST@@CAHPEAPEADPEADPEAHPEAW4SSI_COMMANDS@@PEAW4SSI_TAGS@@1@Z; SSI_ELEMENT_LIST::ParseSSITag(char * *,char *,int *,SSI_COMMANDS *,SSI_TAGS *,char *)
0x180002f2e  test    eax, eax
0x180002f30  jz      short loc_180002F9F
0x180002f32  cmp     [rsp+890h+var_858], 0
0x180002f37  jnz     short loc_180002F48
0x180002f39  mov     rbx, [rsp+890h+var_860]
0x180002f3e  inc     rbx
0x180002f41  mov     [rsp+890h+var_860], rbx
0x180002f46  jmp     short loc_180002F90
0x180002f48  mov     dword ptr [r13+158h], 1
0x180002f53  cmp     rdi, rsi
0x180002f56  jz      short loc_180002F6E
0x180002f58  sub     esi, edi
0x180002f5a  mov     rcx, r13; this
0x180002f5d  sub     edi, r14d
0x180002f60  mov     r8d, esi; unsigned int
0x180002f63  mov     edx, edi; unsigned int
0x180002f65  call    ?AppendByteRange@SSI_ELEMENT_LIST@@AEAAHKK@Z; SSI_ELEMENT_LIST::AppendByteRange(ulong,ulong)
0x180002f6a  test    eax, eax
0x180002f6c  jz      short loc_180002FBF
0x180002f6e  mov     r8d, [rsp+890h+var_854]
0x180002f73  lea     r9, [rsp+890h+var_840]
0x180002f78  mov     edx, [rsp+890h+var_850]
0x180002f7c  mov     rcx, r13
0x180002f7f  call    ?AppendCommand@SSI_ELEMENT_LIST@@AEAAHW4SSI_COMMANDS@@W4SSI_TAGS@@PEAD@Z; SSI_ELEMENT_LIST::AppendCommand(SSI_COMMANDS,SSI_TAGS,char *)
0x180002f84  test    eax, eax
0x180002f86  jz      short loc_180002F98
0x180002f88  mov     rbx, [rsp+890h+var_860]
0x180002f8d  mov     rdi, rbx
0x180002f90  mov     rcx, rbx
0x180002f93  jmp     loc_180002E97
0x180002f98  mov     eax, 80004005h
0x180002f9d  jmp     short loc_180002FD5
0x180002f9f  mov     rbx, [rsp+890h+var_860]
0x180002fa4  cmp     rbx, rdi
0x180002fa7  jbe     short loc_180002FD3
0x180002fa9  sub     ebx, edi
0x180002fab  mov     rcx, r13; this
0x180002fae  sub     edi, r14d
0x180002fb1  mov     r8d, ebx; unsigned int
0x180002fb4  mov     edx, edi; unsigned int
0x180002fb6  call    ?AppendByteRange@SSI_ELEMENT_LIST@@AEAAHKK@Z; SSI_ELEMENT_LIST::AppendByteRange(ulong,ulong)
0x180002fbb  test    eax, eax
0x180002fbd  jnz     short loc_180002FD3
0x180002fbf  call    cs:__imp_GetLastError
0x180002fc5  test    eax, eax
0x180002fc7  jle     short loc_180002FD5
0x180002fc9  movzx   eax, ax
0x180002fcc  or      eax, 80070000h
0x180002fd1  jmp     short loc_180002FD5
0x180002fd3  xor     eax, eax
0x180002fd5  mov     rcx, [rbp+790h+var_30]
0x180002fdc  xor     rcx, rsp; StackCookie
0x180002fdf  call    __security_check_cookie
0x180002fe4  lea     r11, [rsp+890h+var_20]
0x180002fec  mov     rbx, [r11+40h]
0x180002ff0  mov     rsi, [r11+48h]
0x180002ff4  mov     rsp, r11
0x180002ff7  pop     r15
0x180002ff9  pop     r14
0x180002ffb  pop     r13
0x180002ffd  pop     rdi
0x180002ffe  pop     rbp
0x180002fff  retn
```
