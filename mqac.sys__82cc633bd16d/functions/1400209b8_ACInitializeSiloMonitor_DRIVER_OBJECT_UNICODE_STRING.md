# ACInitializeSiloMonitor(_DRIVER_OBJECT *,_UNICODE_STRING *)

- ea: `0x1400209b8`
- end: `0x140020b35`
- name: `?ACInitializeSiloMonitor@@YAJPEAU_DRIVER_OBJECT@@PEAU_UNICODE_STRING@@@Z`
- size: `381`
- prototype: `int(struct _DRIVER_OBJECT *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x14001143c`

## callees

- `0x1400010a4`
- `0x140001128`
- `0x1400209b8`
- `0x140024bb0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140020a4b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140020a4b`
- `ntoskrnl!PsRegisterSiloMonitor` at `0x140020a9d`
- `ntoskrnl!PsRegisterSiloMonitor` at `0x140020a9d`
- `ntoskrnl!PsStartSiloMonitor` at `0x140020ad4`
- `ntoskrnl!PsStartSiloMonitor` at `0x140020ad4`
- `ntoskrnl!PsUnregisterSiloMonitor` at `0x140020b09`
- `ntoskrnl!PsUnregisterSiloMonitor` at `0x140020b09`

## pseudocode

```c
__int64 __fastcall ACInitializeSiloMonitor(struct _DRIVER_OBJECT *a1, struct _UNICODE_STRING *a2)
{
  USHORT v4; // si
  unsigned __int64 v5; // rax
  WCHAR *v6; // rax
  __int64 result; // rax
  int v8; // ebx
  __int16 v9; // [rsp+20h] [rbp-38h] BYREF
  char v10; // [rsp+22h] [rbp-36h]
  int v11; // [rsp+23h] [rbp-35h]
  char v12; // [rsp+27h] [rbp-31h]
  UNICODE_STRING *p_DriverName; // [rsp+28h] [rbp-30h]
  __int64 (__fastcall *v14)(struct _EJOB *); // [rsp+30h] [rbp-28h]
  void (__fastcall *v15)(struct _EJOB *); // [rsp+38h] [rbp-20h]

  v4 = a2->Length + 2;
  v5 = 2 * ((unsigned __int64)v4 >> 1);
  if ( !is_mul_ok((unsigned __int64)v4 >> 1, 2u) )
    v5 = -1;
  v6 = (WCHAR *)operator new(v5, 0x100u, 0x4341514Du, LowPoolPriority);
  if ( !v6 )
    return 3221225626LL;
  g_pDriver = a1;
  g_RegistryPath = 0;
  g_RegistryPath.MaximumLength = v4;
  g_RegistryPath.Buffer = v6;
  RtlCopyUnicodeString(&g_RegistryPath, a2);
  v11 = 0;
  p_DriverName = &a1->DriverName;
  v12 = 0;
  v14 = CreateSiloNotification;
  v9 = 257;
  v15 = TerminateSiloNotification;
  v10 = 1;
  v8 = PsRegisterSiloMonitor(&v9, &g_pSiloMonitor);
  if ( v8 >= 0 )
  {
    result = PsStartSiloMonitor(g_pSiloMonitor);
    v8 = result;
    if ( (int)result >= 0 )
      return result;
    if ( g_RegistryPath.Buffer )
    {
      operator delete(g_RegistryPath.Buffer);
      g_RegistryPath.Buffer = 0;
    }
    PsUnregisterSiloMonitor(g_pSiloMonitor);
  }
  else if ( g_RegistryPath.Buffer )
  {
    operator delete(g_RegistryPath.Buffer);
    g_RegistryPath.Buffer = 0;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400209b8  mov     [rsp+arg_10], rbx
0x1400209bd  mov     [rsp+arg_18], rsi
0x1400209c2  push    rdi
0x1400209c3  sub     rsp, 50h
0x1400209c7  mov     rax, cs:__security_cookie
0x1400209ce  xor     rax, rsp
0x1400209d1  mov     [rsp+58h+var_18], rax
0x1400209d6  mov     rdi, rdx
0x1400209d9  mov     rbx, rcx
0x1400209dc  movzx   edx, word ptr [rdx]
0x1400209df  mov     eax, 2
0x1400209e4  add     dx, ax
0x1400209e7  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1400209ee  movzx   esi, dx
0x1400209f1  mov     r8d, 4341514Dh; unsigned int
0x1400209f7  mov     edx, esi
0x1400209f9  shr     rdx, 1
0x1400209fc  mul     rdx
0x1400209ff  mov     edx, 100h; unsigned __int64
0x140020a04  cmovb   rax, rcx
0x140020a08  xor     r9d, r9d; enum _EX_POOL_PRIORITY
0x140020a0b  mov     rcx, rax; unsigned __int64
0x140020a0e  call    ??2@YAPEAX_K0KW4_EX_POOL_PRIORITY@@@Z; operator new(unsigned __int64,unsigned __int64,ulong,_EX_POOL_PRIORITY)
0x140020a13  test    rax, rax
0x140020a16  jnz     short loc_140020A22
0x140020a18  mov     eax, 0C000009Ah
0x140020a1d  jmp     loc_140020B17
0x140020a22  xorps   xmm0, xmm0
0x140020a25  mov     cs:?g_pDriver@@3PEAU_DRIVER_OBJECT@@EA, rbx; _DRIVER_OBJECT * g_pDriver
0x140020a2c  movups  xmmword ptr cs:?g_RegistryPath@@3U_UNICODE_STRING@@A.Length, xmm0; _UNICODE_STRING g_RegistryPath ...
0x140020a33  mov     rdx, rdi; SourceString
0x140020a36  mov     cs:?g_RegistryPath@@3U_UNICODE_STRING@@A.MaximumLength, si; _UNICODE_STRING g_RegistryPath ...
0x140020a3d  lea     rcx, ?g_RegistryPath@@3U_UNICODE_STRING@@A; DestinationString
0x140020a44  mov     cs:?g_RegistryPath@@3U_UNICODE_STRING@@A.Buffer, rax; _UNICODE_STRING g_RegistryPath ...
0x140020a4b  call    cs:__imp_RtlCopyUnicodeString
0x140020a52  nop     dword ptr [rax+rax+00h]
0x140020a57  lea     rax, [rbx+38h]
0x140020a5b  mov     [rsp+58h+var_35], 0
0x140020a63  mov     [rsp+58h+var_30], rax
0x140020a68  lea     rdx, ?g_pSiloMonitor@@3PEAU_SILO_MONITOR@@EA; _SILO_MONITOR * g_pSiloMonitor
0x140020a6f  lea     rax, ?CreateSiloNotification@@YAJPEAU_EJOB@@@Z; CreateSiloNotification(_EJOB *)
0x140020a76  mov     [rsp+58h+var_31], 0
0x140020a7b  mov     [rsp+58h+var_28], rax
0x140020a80  lea     rcx, [rsp+58h+var_38]
0x140020a85  lea     rax, ?TerminateSiloNotification@@YAXPEAU_EJOB@@@Z; TerminateSiloNotification(_EJOB *)
0x140020a8c  mov     [rsp+58h+var_38], 101h
0x140020a93  mov     [rsp+58h+var_20], rax
0x140020a98  mov     [rsp+58h+var_36], 1
0x140020a9d  call    cs:__imp_PsRegisterSiloMonitor
0x140020aa4  nop     dword ptr [rax+rax+00h]
0x140020aa9  mov     ebx, eax
0x140020aab  test    eax, eax
0x140020aad  jns     short loc_140020ACD
0x140020aaf  mov     rcx, cs:?g_RegistryPath@@3U_UNICODE_STRING@@A.Buffer; void *
0x140020ab6  test    rcx, rcx
0x140020ab9  jz      short loc_140020B15
0x140020abb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140020ac0  mov     cs:?g_RegistryPath@@3U_UNICODE_STRING@@A.Buffer, 0; _UNICODE_STRING g_RegistryPath ...
0x140020acb  jmp     short loc_140020B15
0x140020acd  mov     rcx, cs:?g_pSiloMonitor@@3PEAU_SILO_MONITOR@@EA; _SILO_MONITOR * g_pSiloMonitor
0x140020ad4  call    cs:__imp_PsStartSiloMonitor
0x140020adb  nop     dword ptr [rax+rax+00h]
0x140020ae0  mov     ebx, eax
0x140020ae2  test    eax, eax
0x140020ae4  jns     short loc_140020B17
0x140020ae6  mov     rcx, cs:?g_RegistryPath@@3U_UNICODE_STRING@@A.Buffer; void *
0x140020aed  test    rcx, rcx
0x140020af0  jz      short loc_140020B02
0x140020af2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140020af7  mov     cs:?g_RegistryPath@@3U_UNICODE_STRING@@A.Buffer, 0; _UNICODE_STRING g_RegistryPath ...
0x140020b02  mov     rcx, cs:?g_pSiloMonitor@@3PEAU_SILO_MONITOR@@EA; _SILO_MONITOR * g_pSiloMonitor
0x140020b09  call    cs:__imp_PsUnregisterSiloMonitor
0x140020b10  nop     dword ptr [rax+rax+00h]
0x140020b15  mov     eax, ebx
0x140020b17  mov     rcx, [rsp+58h+var_18]
0x140020b1c  xor     rcx, rsp; StackCookie
0x140020b1f  call    __security_check_cookie
0x140020b24  mov     rbx, [rsp+58h+arg_10]
0x140020b29  mov     rsi, [rsp+58h+arg_18]
0x140020b2e  add     rsp, 50h
0x140020b32  pop     rdi
0x140020b33  retn
```
