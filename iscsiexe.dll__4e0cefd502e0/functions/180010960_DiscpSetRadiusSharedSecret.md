# DiscpSetRadiusSharedSecret

- ea: `0x180010960`
- end: `0x180010b54`
- name: `DiscpSetRadiusSharedSecret`
- size: `500`
- prototype: `__int64 __fastcall(size_t Size, void *Src)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180004120`

## callees

- `0x180006998`
- `0x180010960`
- `0x18001d38c`

## import_xrefs

- `ISCSIUM!DiscpExecuteMethod` at `0x180010ae3`
- `ISCSIUM!DiscpExecuteMethod` at `0x180010ae3`
- `ISCSIUM!DiscpAllocMemory` at `0x18001099f`
- `ISCSIUM!DiscpAllocMemory` at `0x180010a4a`
- `ISCSIUM!DiscpAllocMemory` at `0x18001099f`
- `ISCSIUM!DiscpAllocMemory` at `0x180010a4a`
- `ISCSIUM!DiscpSetRegistryValue` at `0x1800109e8`
- `ISCSIUM!DiscpSetRegistryValue` at `0x1800109e8`
- `ISCSIUM!DiscpFreeMemory` at `0x180010a00`
- `ISCSIUM!DiscpFreeMemory` at `0x180010af7`
- `ISCSIUM!DiscpFreeMemory` at `0x180010b17`
- `ISCSIUM!DiscpFreeMemory` at `0x180010b2f`
- `ISCSIUM!DiscpFreeMemory` at `0x180010b3d`
- `ISCSIUM!DiscpFreeMemory` at `0x180010a00`
- `ISCSIUM!DiscpFreeMemory` at `0x180010af7`
- `ISCSIUM!DiscpFreeMemory` at `0x180010b17`
- `ISCSIUM!DiscpFreeMemory` at `0x180010b2f`
- `ISCSIUM!DiscpFreeMemory` at `0x180010b3d`
- `ntdll!RtlLeaveCriticalSection` at `0x180010a14`
- `ntdll!RtlLeaveCriticalSection` at `0x180010a14`
- `ntdll!RtlEnterCriticalSection` at `0x18001098c`
- `ntdll!RtlEnterCriticalSection` at `0x18001098c`

## pseudocode

```c
__int64 __fastcall DiscpSetRadiusSharedSecret(size_t Size, void *Src)
{
  size_t v2; // rbx
  void *v4; // rax
  __int64 v5; // rsi
  unsigned int InitiatorInstanceList; // edi
  int v7; // r13d
  _DWORD *v8; // rax
  __int64 v9; // r12
  _DWORD *v10; // rsi
  __int64 i; // rbp
  __int64 v12; // r14
  __int64 v13; // r8
  int v14; // ebx
  unsigned int v16; // [rsp+98h] [rbp+10h] BYREF
  __int64 v17; // [rsp+A0h] [rbp+18h] BYREF
  int *v18; // [rsp+A8h] [rbp+20h] BYREF

  v2 = (unsigned int)Size;
  v16 = 0;
  v17 = 0;
  RtlEnterCriticalSection(&DiscpCritSection);
  if ( Src )
  {
    v4 = (void *)DiscpAllocMemory((unsigned int)v2);
    v5 = (__int64)v4;
    if ( !v4 )
    {
      InitiatorInstanceList = 8;
      goto LABEL_10;
    }
    memcpy_0(v4, Src, (unsigned int)v2);
  }
  else
  {
    v5 = 0;
  }
  InitiatorInstanceList = DiscpSetRegistryValue(
                            0,
                            L"Software\\Microsoft\\Windows NT\\CurrentVersion\\iSCSI\\Radius",
                            L"InitiatorRADIUSSecret",
                            3,
                            Src,
                            v2,
                            1);
  if ( !InitiatorInstanceList )
  {
    if ( DiscpRadiusSharedSecret )
      DiscpFreeMemory(DiscpRadiusSharedSecret);
    DiscpRadiusSharedSecret = v5;
  }
LABEL_10:
  RtlLeaveCriticalSection(&DiscpCritSection);
  if ( !InitiatorInstanceList )
  {
    InitiatorInstanceList = DiscpGetInitiatorInstanceList(0, &v16, &v17);
    if ( !InitiatorInstanceList )
    {
      v7 = v2 + 4;
      v8 = (_DWORD *)DiscpAllocMemory((unsigned int)(v2 + 4));
      v9 = v17;
      v10 = v8;
      if ( v8 )
      {
        *v8 = v2;
        if ( Src )
          memcpy_0(v8 + 1, Src, v2);
        for ( i = 0; (unsigned int)i < v16; i = (unsigned int)(i + 1) )
        {
          v12 = *(_QWORD *)(v9 + 8 * i);
          LODWORD(v17) = 260;
          v13 = *(_QWORD *)(v12 + 40);
          v18 = 0;
          if ( (unsigned int)DiscpExecuteMethod(MSiSCSI_Operations_GUID, 0, v13, 72, v10, v7, &v18, &v17, 4)
            || (v14 = *v18, DiscpFreeMemory(v18), v14) )
          {
            InitiatorInstanceList = -1342242770;
          }
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v12 + 16), 0xFFFFFFFF) == 1 )
            DiscpFreeMemory(v12);
        }
        DiscpFreeMemory(v10);
      }
      else
      {
        InitiatorInstanceList = 8;
      }
      DiscpFreeMemory(v9);
    }
  }
  return InitiatorInstanceList;
}

```

## disassembly

```asm
0x180010960  mov     rax, rsp
0x180010963  push    rbx
0x180010964  push    rbp
0x180010965  push    rsi
0x180010966  push    rdi
0x180010967  push    r12
0x180010969  push    r13
0x18001096b  push    r14
0x18001096d  sub     rsp, 50h
0x180010971  mov     ebx, ecx
0x180010973  mov     rbp, rdx
0x180010976  lea     rcx, DiscpCritSection; CriticalSection
0x18001097d  mov     dword ptr [rax+10h], 0
0x180010984  mov     qword ptr [rax+18h], 0
0x18001098c  call    cs:__imp_RtlEnterCriticalSection
0x180010992  mov     r14d, 8
0x180010998  test    rbp, rbp
0x18001099b  jz      short loc_1800109C2
0x18001099d  mov     ecx, ebx
0x18001099f  call    cs:__imp_DiscpAllocMemory
0x1800109a5  mov     rsi, rax
0x1800109a8  test    rax, rax
0x1800109ab  jz      short loc_1800109BD
0x1800109ad  mov     r8d, ebx; Size
0x1800109b0  mov     rdx, rbp; Src
0x1800109b3  mov     rcx, rax; void *
0x1800109b6  call    memcpy_0
0x1800109bb  jmp     short loc_1800109C4
0x1800109bd  mov     edi, r14d
0x1800109c0  jmp     short loc_180010A0D
0x1800109c2  xor     esi, esi
0x1800109c4  mov     byte ptr [rsp+88h+var_58], 1
0x1800109c9  lea     r8, aInitiatorradiu; "InitiatorRADIUSSecret"
0x1800109d0  mov     [rsp+88h+var_60], ebx
0x1800109d4  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800109db  mov     r9d, 3
0x1800109e1  mov     [rsp+88h+var_68], rbp
0x1800109e6  xor     ecx, ecx
0x1800109e8  call    cs:__imp_DiscpSetRegistryValue
0x1800109ee  mov     edi, eax
0x1800109f0  test    eax, eax
0x1800109f2  jnz     short loc_180010A0D
0x1800109f4  mov     rcx, cs:DiscpRadiusSharedSecret
0x1800109fb  test    rcx, rcx
0x1800109fe  jz      short loc_180010A06
0x180010a00  call    cs:__imp_DiscpFreeMemory
0x180010a06  mov     cs:DiscpRadiusSharedSecret, rsi
0x180010a0d  lea     rcx, DiscpCritSection; CriticalSection
0x180010a14  call    cs:__imp_RtlLeaveCriticalSection
0x180010a1a  test    edi, edi
0x180010a1c  jnz     loc_180010B43
0x180010a22  lea     r8, [rsp+88h+arg_10]
0x180010a2a  xor     ecx, ecx
0x180010a2c  lea     rdx, [rsp+88h+arg_8]
0x180010a34  call    DiscpGetInitiatorInstanceList
0x180010a39  mov     edi, eax
0x180010a3b  test    eax, eax
0x180010a3d  jnz     loc_180010B43
0x180010a43  lea     r13d, [rbx+4]
0x180010a47  mov     ecx, r13d
0x180010a4a  call    cs:__imp_DiscpAllocMemory
0x180010a50  mov     r12, [rsp+88h+arg_10]
0x180010a58  mov     rsi, rax
0x180010a5b  test    rax, rax
0x180010a5e  jz      loc_180010B37
0x180010a64  mov     [rax], ebx
0x180010a66  test    rbp, rbp
0x180010a69  jz      short loc_180010A7A
0x180010a6b  mov     r8, rbx; Size
0x180010a6e  lea     rcx, [rax+4]; void *
0x180010a72  mov     rdx, rbp; Src
0x180010a75  call    memcpy_0
0x180010a7a  xor     ebp, ebp
0x180010a7c  cmp     [rsp+88h+arg_8], ebp
0x180010a83  jbe     loc_180010B2C
0x180010a89  mov     r14, [r12+rbp*8]
0x180010a8d  lea     rax, [rsp+88h+arg_10]
0x180010a95  mov     [rsp+88h+var_48], 4
0x180010a9d  lea     rcx, MSiSCSI_Operations_GUID
0x180010aa4  mov     [rsp+88h+var_50], rax
0x180010aa9  mov     r9d, 48h ; 'H'
0x180010aaf  lea     rax, [rsp+88h+arg_18]
0x180010ab7  mov     dword ptr [rsp+88h+arg_10], 104h
0x180010ac2  mov     r8, [r14+28h]
0x180010ac6  xor     edx, edx
0x180010ac8  mov     [rsp+88h+var_58], rax
0x180010acd  mov     [rsp+88h+var_60], r13d
0x180010ad2  mov     [rsp+88h+var_68], rsi
0x180010ad7  mov     [rsp+88h+arg_18], 0
0x180010ae3  call    cs:__imp_DiscpExecuteMethod
0x180010ae9  test    eax, eax
0x180010aeb  jnz     short loc_180010B01
0x180010aed  mov     rcx, [rsp+88h+arg_18]
0x180010af5  mov     ebx, [rcx]
0x180010af7  call    cs:__imp_DiscpFreeMemory
0x180010afd  test    ebx, ebx
0x180010aff  jz      short loc_180010B06
0x180010b01  mov     edi, 0AFFF002Eh
0x180010b06  or      eax, 0FFFFFFFFh
0x180010b09  lock xadd [r14+10h], eax
0x180010b0f  cmp     eax, 1
0x180010b12  jnz     short loc_180010B1D
0x180010b14  mov     rcx, r14
0x180010b17  call    cs:__imp_DiscpFreeMemory
0x180010b1d  inc     ebp
0x180010b1f  cmp     ebp, [rsp+88h+arg_8]
0x180010b26  jb      loc_180010A89
0x180010b2c  mov     rcx, rsi
0x180010b2f  call    cs:__imp_DiscpFreeMemory
0x180010b35  jmp     short loc_180010B3A
0x180010b37  mov     edi, r14d
0x180010b3a  mov     rcx, r12
0x180010b3d  call    cs:__imp_DiscpFreeMemory
0x180010b43  mov     eax, edi
0x180010b45  add     rsp, 50h
0x180010b49  pop     r14
0x180010b4b  pop     r13
0x180010b4d  pop     r12
0x180010b4f  pop     rdi
0x180010b50  pop     rsi
0x180010b51  pop     rbp
0x180010b52  pop     rbx
0x180010b53  retn
```
