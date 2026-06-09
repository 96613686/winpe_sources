# AslLogpWriteEtw(_ASL_LOG *,ASL_LOG_LEVEL,char const *)

- ea: `0x180008bbc`
- end: `0x180008c39`
- name: `?AslLogpWriteEtw@@YAXPEAU_ASL_LOG@@W4ASL_LOG_LEVEL@@PEBD@Z`
- size: `125`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800092ac`

## callees

- `0x180008bbc`
- `0x18000c030`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180008c21`
- `ntdll!EtwEventWrite` at `0x180008c21`

## pseudocode

```c
void __fastcall AslLogpWriteEtw(__int64 a1, int a2, __int64 a3)
{
  __int64 v3; // rcx
  __int64 v4; // rax
  int v5; // edx
  __int64 *v6; // rdx
  __int64 v7; // [rsp+20h] [rbp-28h] BYREF
  int v8; // [rsp+28h] [rbp-20h]
  int v9; // [rsp+2Ch] [rbp-1Ch]

  v3 = *(_QWORD *)(a1 + 712);
  if ( v3 )
  {
    v7 = a3;
    v4 = -1;
    do
      ++v4;
    while ( *(_BYTE *)(a3 + v4) );
    v9 = 0;
    v8 = v4 + 1;
    v5 = a2 - 1;
    if ( v5 )
    {
      if ( v5 != 1 )
        return;
      v6 = AE_MARK_EVENT;
    }
    else
    {
      v6 = AE_DEBUG_EVENT;
    }
    ((void (__fastcall *)(__int64, __int64 *, __int64, __int64 *))EtwEventWrite)(v3, v6, 1, &v7);
  }
}

```

## disassembly

```asm
0x180008bbc  sub     rsp, 48h
0x180008bc0  mov     rax, cs:__security_cookie
0x180008bc7  xor     rax, rsp
0x180008bca  mov     [rsp+48h+var_18], rax
0x180008bcf  mov     rcx, [rcx+2C8h]
0x180008bd6  test    rcx, rcx
0x180008bd9  jz      short loc_180008C27
0x180008bdb  mov     [rsp+48h+var_28], r8
0x180008be0  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008be4  inc     rax
0x180008be7  cmp     byte ptr [r8+rax], 0
0x180008bec  jnz     short loc_180008BE4
0x180008bee  inc     eax
0x180008bf0  mov     [rsp+48h+var_1C], 0
0x180008bf8  mov     [rsp+48h+var_20], eax
0x180008bfc  sub     edx, 1
0x180008bff  jz      short loc_180008C0F
0x180008c01  cmp     edx, 1
0x180008c04  jnz     short loc_180008C27
0x180008c06  lea     rdx, AE_MARK_EVENT
0x180008c0d  jmp     short loc_180008C16
0x180008c0f  lea     rdx, AE_DEBUG_EVENT
0x180008c16  lea     r9, [rsp+48h+var_28]
0x180008c1b  mov     r8d, 1
0x180008c21  call    cs:__imp_EtwEventWrite
0x180008c27  mov     rcx, [rsp+48h+var_18]
0x180008c2c  xor     rcx, rsp; StackCookie
0x180008c2f  call    __security_check_cookie
0x180008c34  add     rsp, 48h
0x180008c38  retn
```
