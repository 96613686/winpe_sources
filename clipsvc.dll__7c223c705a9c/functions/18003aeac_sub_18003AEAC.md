# sub_18003AEAC

- ea: `0x18003aeac`
- end: `0x18003b012`
- name: `sub_18003AEAC`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x18003c01c`

## callees

- `0x1800363f0`
- `0x1800366bc`
- `0x180036708`
- `0x18003ad20`
- `0x18003ad3c`
- `0x18003aeac`
- `0x18003daf4`
- `0x18003dda0`
- `0x18003e6b4`
- `0x18003e8a8`
- `0x1800a6ac0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18003af29`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18003af29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003aee4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003aee4`

## pseudocode

```c
__int64 __fastcall sub_18003AEAC(__int64 a1, _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  unsigned int v6; // ebx
  int v7; // eax
  __int64 v8; // rdx
  _DWORD *v9; // rcx
  __int64 v11; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v12[8]; // [rsp+38h] [rbp-C8h] BYREF
  _DWORD *v13; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  void *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  sub_18003DAF4(Name, 260, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId, 120, a1);
  v11 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  sub_18003E8A8(&v11, Mutex);
  if ( v11 )
  {
    sub_18003E6B4(&v11, v12);
    v13 = 0;
    v7 = sub_18003DDA0(Name, &v13);
    v6 = v7;
    if ( v7 < 0 )
    {
      v8 = 302;
LABEL_5:
      sub_1800366BC(retaddr, v8, "wil", (unsigned int)v7);
      sub_18003AD3C(v12);
      goto LABEL_9;
    }
    v9 = v13;
    if ( v13 )
    {
      *a2 = v13;
      ++*v9;
    }
    else
    {
      v7 = sub_1800363F0(Name, &v11, a2);
      v6 = v7;
      if ( v7 < 0 )
      {
        v8 = 311;
        goto LABEL_5;
      }
    }
    sub_18003AD3C(v12);
    v6 = 0;
    goto LABEL_9;
  }
  v6 = sub_180036708();
LABEL_9:
  sub_18003AD20(&v11);
  return v6;
}

```

## disassembly

```asm
0x18003aeac  mov     [rsp-8+arg_10], rbx
0x18003aeb1  mov     [rsp-8+arg_18], rdi
0x18003aeb6  push    rbp
0x18003aeb7  lea     rbp, [rsp-170h]
0x18003aebf  sub     rsp, 270h
0x18003aec6  mov     rax, cs:__security_cookie
0x18003aecd  xor     rax, rsp
0x18003aed0  mov     [rbp+170h+var_10], rax
0x18003aed7  mov     rdi, rdx
0x18003aeda  mov     qword ptr [rdx], 0
0x18003aee1  mov     rbx, rcx
0x18003aee4  call    cs:GetCurrentProcessId
0x18003aeea  mov     [rsp+270h+var_248], rbx
0x18003aeef  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18003aef6  mov     r9d, eax
0x18003aef9  mov     [rsp+270h+var_250], 78h ; 'x'
0x18003af01  mov     edx, 104h
0x18003af06  lea     rcx, [rsp+270h+Name]
0x18003af0b  call    sub_18003DAF4
0x18003af10  mov     r9d, 1F0001h; dwDesiredAccess
0x18003af16  mov     [rsp+270h+var_240], 0
0x18003af1f  xor     r8d, r8d; dwFlags
0x18003af22  lea     rdx, [rsp+270h+Name]; lpName
0x18003af27  xor     ecx, ecx; lpMutexAttributes
0x18003af29  call    cs:CreateMutexExW
0x18003af2f  mov     rdx, rax
0x18003af32  lea     rcx, [rsp+270h+var_240]
0x18003af37  call    sub_18003E8A8
0x18003af3c  cmp     [rsp+270h+var_240], 0
0x18003af42  jnz     short loc_18003AF4D
0x18003af44  call    sub_180036708
0x18003af49  mov     ebx, eax
0x18003af4b  jmp     short loc_18003AFC0
0x18003af4d  lea     rdx, [rsp+270h+var_238]
0x18003af52  lea     rcx, [rsp+270h+var_240]
0x18003af57  call    sub_18003E6B4
0x18003af5c  lea     rdx, [rsp+270h+var_230]
0x18003af61  mov     [rsp+270h+var_230], 0
0x18003af6a  lea     rcx, [rsp+270h+Name]
0x18003af6f  call    sub_18003DDA0
0x18003af74  mov     ebx, eax
0x18003af76  test    eax, eax
0x18003af78  jns     short loc_18003AFA1
0x18003af7a  mov     edx, 12Eh
0x18003af7f  mov     rcx, [rbp+178h]
0x18003af86  lea     r8, aWil; "wil"
0x18003af8d  mov     r9d, eax
0x18003af90  call    sub_1800366BC
0x18003af95  lea     rcx, [rsp+270h+var_238]
0x18003af9a  call    sub_18003AD3C
0x18003af9f  jmp     short loc_18003AFC0
0x18003afa1  mov     rcx, [rsp+270h+var_230]
0x18003afa6  test    rcx, rcx
0x18003afa9  jz      short loc_18003AFF0
0x18003afab  mov     [rdi], rcx
0x18003afae  mov     eax, [rcx]
0x18003afb0  inc     eax
0x18003afb2  mov     [rcx], eax
0x18003afb4  lea     rcx, [rsp+270h+var_238]
0x18003afb9  call    sub_18003AD3C
0x18003afbe  xor     ebx, ebx
0x18003afc0  lea     rcx, [rsp+270h+var_240]
0x18003afc5  call    sub_18003AD20
0x18003afca  mov     eax, ebx
0x18003afcc  mov     rcx, [rbp+170h+var_10]
0x18003afd3  xor     rcx, rsp; StackCookie
0x18003afd6  call    __security_check_cookie
0x18003afdb  lea     r11, [rsp+270h+var_s0]
0x18003afe3  mov     rbx, [r11+20h]
0x18003afe7  mov     rdi, [r11+28h]
0x18003afeb  mov     rsp, r11
0x18003afee  pop     rbp
0x18003afef  retn
0x18003aff0  mov     r8, rdi
0x18003aff3  lea     rdx, [rsp+270h+var_240]
0x18003aff8  lea     rcx, [rsp+270h+Name]
0x18003affd  call    sub_1800363F0
0x18003b002  mov     ebx, eax
0x18003b004  test    eax, eax
0x18003b006  jns     short loc_18003AFB4
0x18003b008  mov     edx, 137h
0x18003b00d  jmp     loc_18003AF7F
```
