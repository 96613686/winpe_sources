# CGPServiceState::InitializeFromServiceId(ushort const *)

- ea: `0x18002c220`
- end: `0x18002c46f`
- name: `?InitializeFromServiceId@CGPServiceState@@AEAAKPEBG@Z`
- size: `591`
- prototype: `unsigned int __fastcall(CGPServiceState *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002c194`

## callees

- `0x18002c220`
- `0x18002c478`
- `0x1800382cc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002c2da`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002c2da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c383`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c383`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c3fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c405`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c3fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c405`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002c28a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002c3e2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002c28a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002c3e2`

## string_xrefs

- `0x18002c25a`: `Software\Microsoft\Windows\CurrentVersion\Group Policy\ServiceInstances`

## pseudocode

```c
__int64 __fastcall CGPServiceState::InitializeFromServiceId(CGPServiceState *this, const unsigned __int16 *a2)
{
  HLOCAL *v3; // r14
  unsigned int StringGuid; // ebx
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // rbx
  _WORD *v7; // rax
  _WORD *v8; // r8
  __int64 v9; // rcx
  const unsigned __int16 *v10; // rdx
  int v11; // esi
  const WCHAR *v13; // rdx
  CGuid *v14; // rax
  HKEY lpdwDisposition; // [rsp+80h] [rbp+8h] BYREF
  DWORD dwDisposition; // [rsp+88h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+90h] [rbp+18h] BYREF

  v3 = (HLOCAL *)((char *)this + 8);
  dwDisposition = 0;
  hKey = 0;
  if ( *((_QWORD *)this + 1) )
  {
    StringGuid = 183;
  }
  else
  {
    LODWORD(lpdwDisposition) = 0;
    StringGuid = RegCreateKeyExW(
                   HKEY_LOCAL_MACHINE,
                   L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\ServiceInstances",
                   0,
                   0,
                   1u,
                   0x2001Fu,
                   0,
                   &hKey,
                   (LPDWORD)&lpdwDisposition);
  }
  if ( a2 )
  {
    v5 = -1;
    do
      ++v5;
    while ( a2[v5] );
    v6 = v5 + 1;
    if ( v5 + 1 >= v5 && (lpdwDisposition = 0, is_mul_ok(v6, 2u)) )
    {
      v7 = LocalAlloc(0x40u, 2 * v6);
      *v3 = v7;
      v8 = v7;
      if ( !v7 )
      {
        StringGuid = 14;
        goto LABEL_17;
      }
      if ( v6 )
      {
        if ( v6 > 0x7FFFFFFF )
        {
          LOWORD(v11) = 87;
          *v7 = 0;
        }
        else
        {
          v9 = 2147483646;
          v10 = a2;
          v11 = 0;
          while ( v9 && *v10 )
          {
            *v8++ = *v10++;
            --v9;
            if ( !--v6 )
            {
              --v8;
              v11 = -2147024774;
              break;
            }
          }
          *v8 = 0;
          if ( v11 >= 0 )
          {
            StringGuid = 0;
            goto LABEL_17;
          }
        }
      }
      else
      {
        LOWORD(v11) = 87;
      }
      LocalFree(*v3);
      *v3 = 0;
      StringGuid = (unsigned __int16)v11;
    }
    else
    {
      StringGuid = 534;
    }
  }
  else
  {
    if ( StringGuid )
      goto LABEL_18;
    v14 = CGuid::Create();
    if ( !v14 )
    {
      StringGuid = 14;
      goto LABEL_18;
    }
    StringGuid = CGuid::GetStringGuid(v14, (unsigned __int16 **)v3);
  }
LABEL_17:
  if ( !StringGuid && !a2 )
  {
    v13 = (const WCHAR *)*v3;
    lpdwDisposition = 0;
    StringGuid = RegCreateKeyExW(hKey, v13, 0, 0, 1u, 0x20019u, 0, &lpdwDisposition, &dwDisposition);
    if ( !StringGuid )
      RegCloseKey(lpdwDisposition);
  }
LABEL_18:
  if ( hKey )
    RegCloseKey(hKey);
  return StringGuid;
}

```

## disassembly

```asm
0x18002c220  mov     r11, rsp
0x18002c223  push    rbx
0x18002c224  sub     rsp, 70h
0x18002c228  mov     [r11-10h], rbp
0x18002c22c  xor     ebp, ebp
0x18002c22e  mov     [r11-20h], rdi
0x18002c232  mov     rdi, rdx
0x18002c235  mov     [r11-28h], r14
0x18002c239  lea     r14, [rcx+8]
0x18002c23d  mov     [r11+10h], ebp
0x18002c241  mov     [r11+18h], rbp
0x18002c245  cmp     [r14], rbp
0x18002c248  jnz     loc_18002C41A
0x18002c24e  lea     rax, [r11+8]
0x18002c252  mov     [r11+8], ebp
0x18002c256  mov     [r11-38h], rax
0x18002c25a  lea     rdx, aSoftwareMicros_32; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002c261  lea     rax, [r11+18h]
0x18002c265  xor     r9d, r9d; lpClass
0x18002c268  mov     [r11-40h], rax
0x18002c26c  xor     r8d, r8d; Reserved
0x18002c26f  mov     [r11-48h], rbp
0x18002c273  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002c27a  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x18002c282  mov     [rsp+78h+dwOptions], 1; dwOptions
0x18002c28a  call    cs:__imp_RegCreateKeyExW
0x18002c290  mov     ebx, eax
0x18002c292  mov     [rsp+78h+var_18], rsi
0x18002c297  test    rdi, rdi
0x18002c29a  jz      loc_18002C424
0x18002c2a0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18002c2a7  inc     rax
0x18002c2aa  cmp     [rdi+rax*2], bp
0x18002c2ae  jnz     short loc_18002C2A7
0x18002c2b0  lea     rbx, [rax+1]
0x18002c2b4  cmp     rbx, rax
0x18002c2b7  jb      loc_18002C33D
0x18002c2bd  mov     eax, 2
0x18002c2c2  mov     [rsp+78h+arg_0], rbp
0x18002c2ca  mul     rbx
0x18002c2cd  test    rdx, rdx
0x18002c2d0  jnz     short loc_18002C33D
0x18002c2d2  mov     rdx, rax; uBytes
0x18002c2d5  mov     ecx, 40h ; '@'; uFlags
0x18002c2da  call    cs:__imp_LocalAlloc
0x18002c2e0  mov     [r14], rax
0x18002c2e3  mov     r8, rax
0x18002c2e6  test    rax, rax
0x18002c2e9  jz      loc_18002C410
0x18002c2ef  test    rbx, rbx
0x18002c2f2  jz      loc_18002C459
0x18002c2f8  cmp     rbx, 7FFFFFFFh
0x18002c2ff  ja      loc_18002C452
0x18002c305  mov     ecx, 7FFFFFFEh
0x18002c30a  mov     rdx, rdi
0x18002c30d  mov     esi, ebp
0x18002c30f  nop
0x18002c310  test    rcx, rcx
0x18002c313  jz      short loc_18002C378
0x18002c315  movzx   eax, word ptr [rdx]
0x18002c318  test    ax, ax
0x18002c31b  jz      short loc_18002C373
0x18002c31d  mov     [r8], ax
0x18002c321  add     rdx, 2
0x18002c325  add     r8, 2
0x18002c329  dec     rcx
0x18002c32c  sub     rbx, 1
0x18002c330  jnz     short loc_18002C310
0x18002c332  sub     r8, 2
0x18002c336  mov     esi, 8007007Ah
0x18002c33b  jmp     short loc_18002C378
0x18002c33d  mov     ebx, 216h
0x18002c342  test    ebx, ebx
0x18002c344  jz      short loc_18002C395
0x18002c346  mov     rcx, [rsp+78h+hKey]; hKey
0x18002c34e  mov     r14, [rsp+78h+var_28]
0x18002c353  mov     rdi, [rsp+78h+var_20]
0x18002c358  mov     rsi, [rsp+78h+var_18]
0x18002c35d  mov     rbp, [rsp+78h+var_10]
0x18002c362  test    rcx, rcx
0x18002c365  jnz     loc_18002C405
0x18002c36b  mov     eax, ebx
0x18002c36d  add     rsp, 70h
0x18002c371  pop     rbx
0x18002c372  retn
0x18002c373  test    rbx, rbx
0x18002c376  jz      short loc_18002C332
0x18002c378  mov     [r8], bp
0x18002c37c  test    esi, esi
0x18002c37e  jns     short loc_18002C391
0x18002c380  mov     rcx, [r14]; hMem
0x18002c383  call    cs:__imp_LocalFree
0x18002c389  mov     [r14], rbp
0x18002c38c  movzx   ebx, si
0x18002c38f  jmp     short loc_18002C342
0x18002c391  mov     ebx, ebp
0x18002c393  jmp     short loc_18002C342
0x18002c395  test    rdi, rdi
0x18002c398  jnz     short loc_18002C346
0x18002c39a  mov     rdx, [r14]; lpSubKey
0x18002c39d  lea     rax, [rsp+78h+dwDisposition]
0x18002c3a5  mov     rcx, [rsp+78h+hKey]; hKey
0x18002c3ad  xor     r9d, r9d; lpClass
0x18002c3b0  mov     [rsp+78h+lpdwDisposition], rax; lpdwDisposition
0x18002c3b5  xor     r8d, r8d; Reserved
0x18002c3b8  lea     rax, [rsp+78h+arg_0]
0x18002c3c0  mov     [rsp+78h+arg_0], rbp
0x18002c3c8  mov     [rsp+78h+phkResult], rax; phkResult
0x18002c3cd  mov     [rsp+78h+lpSecurityAttributes], rbp; lpSecurityAttributes
0x18002c3d2  mov     [rsp+78h+samDesired], 20019h; samDesired
0x18002c3da  mov     [rsp+78h+dwOptions], 1; dwOptions
0x18002c3e2  call    cs:__imp_RegCreateKeyExW
0x18002c3e8  mov     ebx, eax
0x18002c3ea  test    eax, eax
0x18002c3ec  jnz     loc_18002C346
0x18002c3f2  mov     rcx, [rsp+78h+arg_0]; hKey
0x18002c3fa  call    cs:__imp_RegCloseKey
0x18002c400  jmp     loc_18002C346
0x18002c405  call    cs:__imp_RegCloseKey
0x18002c40b  jmp     loc_18002C36B
0x18002c410  mov     ebx, 0Eh
0x18002c415  jmp     loc_18002C342
0x18002c41a  mov     ebx, 0B7h
0x18002c41f  jmp     loc_18002C292
0x18002c424  test    ebx, ebx
0x18002c426  jnz     loc_18002C346
0x18002c42c  call    ?Create@CGuid@@SAPEAV1@XZ; CGuid::Create(void)
0x18002c431  test    rax, rax
0x18002c434  jnz     short loc_18002C440
0x18002c436  mov     ebx, 0Eh
0x18002c43b  jmp     loc_18002C346
0x18002c440  mov     rdx, r14; unsigned __int16 **
0x18002c443  mov     rcx, rax; this
0x18002c446  call    ?GetStringGuid@CGuid@@QEAAKPEAPEAG@Z; CGuid::GetStringGuid(ushort * *)
0x18002c44b  mov     ebx, eax
0x18002c44d  jmp     loc_18002C342
0x18002c452  mov     esi, 80070057h
0x18002c457  jmp     short loc_18002C467
0x18002c459  mov     esi, 80070057h
0x18002c45e  test    rbx, rbx
0x18002c461  jz      loc_18002C380
0x18002c467  mov     [rax], bp
0x18002c46a  jmp     loc_18002C380
```
