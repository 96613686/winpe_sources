# GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)

- ea: `0x18003ce5c`
- end: `0x18003cfed`
- name: `?GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z`
- size: `401`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18003cff4`

## callees

- `0x1800029c0`
- `0x180003e4c`
- `0x18000a9c0`
- `0x18000c230`
- `0x1800128ec`
- `0x18003ce5c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003cedb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003cf50`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003cedb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003cf50`

## pseudocode

```c
__int64 __fastcall GetRegistryString(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  void *pvData; // rdi
  int ValueW; // ebx
  unsigned __int64 v8; // rax
  bool v9; // sf
  struct _LIST_ENTRY *v10; // rcx
  const unsigned __int16 *pcbData; // [rsp+68h] [rbp+10h] BYREF

  pcbData = a2;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 15, WPP_fb8bb33ffd963c24ba2489b93340fa72_Traceguids);
  }
  pvData = 0;
  LODWORD(pcbData) = 0;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\dot3svc\\MigrationData\\GP_Policy",
             a3,
             2u,
             0,
             0,
             (LPDWORD)&pcbData);
  if ( ValueW )
    goto LABEL_11;
  LODWORD(pcbData) = (_DWORD)pcbData + 4;
  v8 = 2 * ((unsigned __int64)(unsigned int)pcbData >> 1);
  if ( !is_mul_ok((unsigned __int64)(unsigned int)pcbData >> 1, 2u) )
    v8 = -1;
  pvData = operator new[](v8, (const struct std::nothrow_t *)std::nothrow);
  if ( !pvData )
  {
    LOWORD(ValueW) = 14;
LABEL_12:
    ValueW = (unsigned __int16)ValueW | 0x80070000;
    goto LABEL_13;
  }
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\dot3svc\\MigrationData\\GP_Policy",
             a3,
             2u,
             0,
             pvData,
             (LPDWORD)&pcbData);
  if ( ValueW )
  {
LABEL_11:
    v9 = ValueW < 0;
    if ( ValueW <= 0 )
      goto LABEL_14;
    goto LABEL_12;
  }
  *a4 = (unsigned __int16 *)pvData;
LABEL_13:
  v9 = ValueW < 0;
LABEL_14:
  if ( !v9 )
  {
LABEL_18:
    v10 = WPP_GLOBAL_Control;
    goto LABEL_19;
  }
  operator delete(pvData);
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    return (unsigned int)ValueW;
  if ( (BYTE4(WPP_GLOBAL_Control[1].Blink) & 2) != 0 )
  {
    WPP_SF_SS(
      WPP_GLOBAL_Control[1].Flink,
      16,
      (unsigned int)WPP_fb8bb33ffd963c24ba2489b93340fa72_Traceguids,
      (unsigned int)L"Software\\Microsoft\\dot3svc\\MigrationData\\GP_Policy",
      (__int64)a3);
    goto LABEL_18;
  }
LABEL_19:
  if ( v10 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v10[1].Blink) & 0x10) != 0 )
    WPP_SF_d(v10[1].Flink, 17, WPP_fb8bb33ffd963c24ba2489b93340fa72_Traceguids, (unsigned int)ValueW);
  return (unsigned int)ValueW;
}

```

## disassembly

```asm
0x18003ce5c  mov     [rsp+arg_0], rbx
0x18003ce61  mov     [rsp+arg_10], rsi
0x18003ce66  mov     [rsp+arg_8], rdx
0x18003ce6b  push    rdi
0x18003ce6c  push    r14
0x18003ce6e  push    r15
0x18003ce70  sub     rsp, 40h
0x18003ce74  mov     r14, r9
0x18003ce77  mov     rsi, r8
0x18003ce7a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ce81  lea     r15, WPP_GLOBAL_Control
0x18003ce88  cmp     rcx, r15
0x18003ce8b  jz      short loc_18003CEA8
0x18003ce8d  test    byte ptr [rcx+1Ch], 10h
0x18003ce91  jz      short loc_18003CEA8
0x18003ce93  mov     rcx, [rcx+10h]
0x18003ce97  lea     r8, WPP_fb8bb33ffd963c24ba2489b93340fa72_Traceguids
0x18003ce9e  mov     edx, 0Fh
0x18003cea3  call    WPP_SF_
0x18003cea8  xor     edi, edi
0x18003ceaa  mov     dword ptr [rsp+58h+arg_8], 0
0x18003ceb2  lea     rax, [rsp+58h+arg_8]
0x18003ceb7  mov     r8, rsi; lpValue
0x18003ceba  mov     [rsp+58h+pcbData], rax; pcbData
0x18003cebf  lea     rdx, aSoftwareMicros_9; "Software\\Microsoft\\dot3svc\\Migration"...
0x18003cec6  mov     [rsp+58h+pvData], rdi; pvData
0x18003cecb  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18003ced2  lea     r9d, [rdi+2]; dwFlags
0x18003ced6  mov     [rsp+58h+pdwType], rdi; pdwType
0x18003cedb  call    cs:__imp_RegGetValueW
0x18003cee1  mov     ebx, eax
0x18003cee3  test    eax, eax
0x18003cee5  jnz     short loc_18003CF61
0x18003cee7  mov     eax, dword ptr [rsp+58h+arg_8]
0x18003ceeb  add     eax, 4
0x18003ceee  mov     ecx, eax
0x18003cef0  mov     dword ptr [rsp+58h+arg_8], eax
0x18003cef4  lea     eax, [rdi+2]
0x18003cef7  shr     rcx, 1
0x18003cefa  mul     rcx
0x18003cefd  lea     rcx, [rdi-1]
0x18003cf01  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003cf08  cmovb   rax, rcx
0x18003cf0c  mov     rcx, rax; unsigned __int64
0x18003cf0f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003cf14  mov     rdi, rax
0x18003cf17  test    rax, rax
0x18003cf1a  jnz     short loc_18003CF21
0x18003cf1c  lea     ebx, [rax+0Eh]
0x18003cf1f  jmp     short loc_18003CF65
0x18003cf21  lea     rax, [rsp+58h+arg_8]
0x18003cf26  mov     r9d, 2; dwFlags
0x18003cf2c  mov     [rsp+58h+pcbData], rax; pcbData
0x18003cf31  lea     rdx, aSoftwareMicros_9; "Software\\Microsoft\\dot3svc\\Migration"...
0x18003cf38  mov     [rsp+58h+pvData], rdi; pvData
0x18003cf3d  mov     r8, rsi; lpValue
0x18003cf40  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18003cf47  mov     [rsp+58h+pdwType], 0; pdwType
0x18003cf50  call    cs:__imp_RegGetValueW
0x18003cf56  mov     ebx, eax
0x18003cf58  test    eax, eax
0x18003cf5a  jnz     short loc_18003CF61
0x18003cf5c  mov     [r14], rdi
0x18003cf5f  jmp     short loc_18003CF6E
0x18003cf61  test    ebx, ebx
0x18003cf63  jle     short loc_18003CF70
0x18003cf65  movzx   ebx, bx
0x18003cf68  or      ebx, 80070000h
0x18003cf6e  test    ebx, ebx
0x18003cf70  jns     short loc_18003CFAD
0x18003cf72  mov     rcx, rdi; Block
0x18003cf75  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003cf7a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cf81  cmp     rcx, r15
0x18003cf84  jz      short loc_18003CFD7
0x18003cf86  test    byte ptr [rcx+1Ch], 2
0x18003cf8a  jz      short loc_18003CFB4
0x18003cf8c  mov     rcx, [rcx+10h]
0x18003cf90  lea     r9, aSoftwareMicros_9; "Software\\Microsoft\\dot3svc\\Migration"...
0x18003cf97  mov     edx, 10h
0x18003cf9c  mov     [rsp+58h+pdwType], rsi
0x18003cfa1  lea     r8, WPP_fb8bb33ffd963c24ba2489b93340fa72_Traceguids
0x18003cfa8  call    WPP_SF_SS
0x18003cfad  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cfb4  cmp     rcx, r15
0x18003cfb7  jz      short loc_18003CFD7
0x18003cfb9  test    byte ptr [rcx+1Ch], 10h
0x18003cfbd  jz      short loc_18003CFD7
0x18003cfbf  mov     rcx, [rcx+10h]
0x18003cfc3  lea     r8, WPP_fb8bb33ffd963c24ba2489b93340fa72_Traceguids
0x18003cfca  mov     edx, 11h
0x18003cfcf  mov     r9d, ebx
0x18003cfd2  call    WPP_SF_d
0x18003cfd7  mov     rsi, [rsp+58h+arg_10]
0x18003cfdc  mov     eax, ebx
0x18003cfde  mov     rbx, [rsp+58h+arg_0]
0x18003cfe3  add     rsp, 40h
0x18003cfe7  pop     r15
0x18003cfe9  pop     r14
0x18003cfeb  pop     rdi
0x18003cfec  retn
```
