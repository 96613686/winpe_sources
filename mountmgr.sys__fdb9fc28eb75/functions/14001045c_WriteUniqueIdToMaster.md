# WriteUniqueIdToMaster

- ea: `0x14001045c`
- end: `0x1400105ec`
- name: `WriteUniqueIdToMaster`
- size: `400`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400119a0`

## callees

- `0x140001ae0`
- `0x140001b30`
- `0x140002f80`
- `0x14000be4c`
- `0x14001045c`

## import_xrefs

- `ntoskrnl!RtlWriteRegistryValue` at `0x140010517`
- `ntoskrnl!RtlWriteRegistryValue` at `0x140010517`
- `ntoskrnl!ExAllocatePool2` at `0x14001048c`
- `ntoskrnl!ExAllocatePool2` at `0x14001048c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001055a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001055a`
- `ntoskrnl!RtlCompareMemory` at `0x1400105ac`
- `ntoskrnl!RtlCompareMemory` at `0x1400105ac`

## string_xrefs

- `0x1400104e8`: `\Registry\Machine\System\MountedDevices`

## pseudocode

```c
__int64 __fastcall WriteUniqueIdToMaster(_QWORD *Context, unsigned __int16 *a2)
{
  __int64 v4; // rdx
  WCHAR *Pool2; // rax
  WCHAR *v6; // rbx
  NTSTATUS v8; // ebp
  __int64 v9; // r8
  char *v10; // r14
  char *v11; // rdi
  _WORD *v12; // rdx
  __int64 v13; // r12
  SIZE_T v14; // rbx
  UNICODE_STRING v15; // [rsp+30h] [rbp-48h] BYREF

  v4 = a2[5] + 2LL;
  v15 = 0;
  Pool2 = (WCHAR *)ExAllocatePool2(258, v4, 1098149453);
  v6 = Pool2;
  if ( Pool2 )
  {
    memmove(Pool2, (char *)a2 + a2[4], a2[5]);
    v6[(unsigned __int64)a2[5] >> 1] = 0;
    v8 = RtlWriteRegistryValue(0, L"\\Registry\\Machine\\System\\MountedDevices", v6, 3u, (char *)a2 + a2[6], a2[7]);
    if ( v8 < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 120, v9, (unsigned int)v8);
    }
    ExFreePoolWithTag(v6, 0);
    v10 = (char *)(Context + 2);
    v11 = (char *)Context[2];
    v15.MaximumLength = a2[5];
    v15.Length = v15.MaximumLength;
    v15.Buffer = (unsigned __int16 *)((char *)a2 + a2[4]);
    if ( v11 != (char *)(Context + 2) )
    {
      do
      {
        v12 = (_WORD *)*((_QWORD *)v11 + 12);
        v13 = (__int64)v11;
        if ( a2[7] == *v12 )
        {
          v14 = a2[7];
          if ( RtlCompareMemory((char *)a2 + a2[6], v12 + 1, v14) == v14 )
            break;
        }
        v11 = *(char **)v11;
      }
      while ( v11 != v10 );
      if ( v11 != v10 )
        MountMgrCreatePointWorker(Context, &v15, v13);
    }
    return (unsigned int)v8;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 119);
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x14001045c  push    rbx
0x14001045e  push    rbp
0x14001045f  push    rsi
0x140010460  push    rdi
0x140010461  push    r12
0x140010463  push    r14
0x140010465  push    r15
0x140010467  sub     rsp, 40h
0x14001046b  mov     rsi, rdx
0x14001046e  mov     r15, rcx
0x140010471  movzx   edx, word ptr [rdx+0Ah]
0x140010475  xorps   xmm0, xmm0
0x140010478  add     rdx, 2
0x14001047c  mov     ecx, 102h
0x140010481  mov     r8d, 41746E4Dh
0x140010487  movups  xmmword ptr [rsp+78h+var_48.Length], xmm0
0x14001048c  call    cs:__imp_ExAllocatePool2
0x140010493  nop     dword ptr [rax+rax+00h]
0x140010498  mov     rbx, rax
0x14001049b  test    rax, rax
0x14001049e  jnz     short loc_1400104D0
0x1400104a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400104a7  lea     rax, WPP_GLOBAL_Control
0x1400104ae  cmp     rcx, rax
0x1400104b1  jz      short loc_1400104C6
0x1400104b3  mov     eax, [rcx+2Ch]
0x1400104b6  test    al, 4
0x1400104b8  jz      short loc_1400104C6
0x1400104ba  mov     rcx, [rcx+18h]
0x1400104be  lea     edx, [rbx+77h]
0x1400104c1  call    WPP_SF_
0x1400104c6  mov     eax, 0C000009Ah
0x1400104cb  jmp     loc_1400105DC
0x1400104d0  movzx   edx, word ptr [rsi+8]
0x1400104d4  mov     rcx, rbx; void *
0x1400104d7  movzx   r8d, word ptr [rsi+0Ah]; Size
0x1400104dc  add     rdx, rsi; Src
0x1400104df  call    memmove
0x1400104e4  movzx   ecx, word ptr [rsi+0Ah]
0x1400104e8  lea     rdx, Path; "\\Registry\\Machine\\System\\MountedDev"...
0x1400104ef  shr     rcx, 1
0x1400104f2  xor     eax, eax
0x1400104f4  mov     r9d, 3; ValueType
0x1400104fa  mov     r8, rbx; ValueName
0x1400104fd  mov     [rbx+rcx*2], ax
0x140010501  movzx   ecx, word ptr [rsi+0Ch]
0x140010505  movzx   eax, word ptr [rsi+0Eh]
0x140010509  add     rcx, rsi
0x14001050c  mov     [rsp+78h+ValueLength], eax; ValueLength
0x140010510  mov     [rsp+78h+ValueData], rcx; ValueData
0x140010515  xor     ecx, ecx; RelativeTo
0x140010517  call    cs:__imp_RtlWriteRegistryValue
0x14001051e  nop     dword ptr [rax+rax+00h]
0x140010523  mov     ebp, eax
0x140010525  test    eax, eax
0x140010527  jns     short loc_140010555
0x140010529  mov     rcx, cs:WPP_GLOBAL_Control
0x140010530  lea     rax, WPP_GLOBAL_Control
0x140010537  cmp     rcx, rax
0x14001053a  jz      short loc_140010555
0x14001053c  mov     edx, [rcx+2Ch]
0x14001053f  test    dl, 1
0x140010542  jz      short loc_140010555
0x140010544  mov     rcx, [rcx+18h]
0x140010548  mov     edx, 78h ; 'x'
0x14001054d  mov     r9d, ebp
0x140010550  call    WPP_SF_L
0x140010555  xor     edx, edx; Tag
0x140010557  mov     rcx, rbx; P
0x14001055a  call    cs:__imp_ExFreePoolWithTag
0x140010561  nop     dword ptr [rax+rax+00h]
0x140010566  movzx   eax, word ptr [rsi+0Ah]
0x14001056a  lea     r14, [r15+10h]
0x14001056e  mov     rdi, [r14]
0x140010571  mov     [rsp+78h+var_48.MaximumLength], ax
0x140010576  mov     [rsp+78h+var_48.Length], ax
0x14001057b  movzx   eax, word ptr [rsi+8]
0x14001057f  add     rax, rsi
0x140010582  mov     [rsp+78h+var_48.Buffer], rax
0x140010587  cmp     rdi, r14
0x14001058a  jz      short loc_1400105DA
0x14001058c  mov     rdx, [rdi+60h]
0x140010590  mov     r12, rdi
0x140010593  movzx   eax, word ptr [rsi+0Eh]
0x140010597  cmp     ax, [rdx]
0x14001059a  jnz     short loc_1400105BD
0x14001059c  movzx   ecx, word ptr [rsi+0Ch]
0x1400105a0  add     rdx, 2; Source2
0x1400105a4  add     rcx, rsi; Source1
0x1400105a7  mov     r8d, eax; Length
0x1400105aa  mov     ebx, eax
0x1400105ac  call    cs:__imp_RtlCompareMemory
0x1400105b3  nop     dword ptr [rax+rax+00h]
0x1400105b8  cmp     rax, rbx
0x1400105bb  jz      short loc_1400105C5
0x1400105bd  mov     rdi, [rdi]
0x1400105c0  cmp     rdi, r14
0x1400105c3  jnz     short loc_14001058C
0x1400105c5  cmp     rdi, r14
0x1400105c8  jz      short loc_1400105DA
0x1400105ca  mov     r8, r12
0x1400105cd  lea     rdx, [rsp+78h+var_48]
0x1400105d2  mov     rcx, r15; Context
0x1400105d5  call    MountMgrCreatePointWorker
0x1400105da  mov     eax, ebp
0x1400105dc  add     rsp, 40h
0x1400105e0  pop     r15
0x1400105e2  pop     r14
0x1400105e4  pop     r12
0x1400105e6  pop     rdi
0x1400105e7  pop     rsi
0x1400105e8  pop     rbp
0x1400105e9  pop     rbx
0x1400105ea  retn
```
