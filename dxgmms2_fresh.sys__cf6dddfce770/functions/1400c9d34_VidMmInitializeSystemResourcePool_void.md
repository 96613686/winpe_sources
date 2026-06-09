# VidMmInitializeSystemResourcePool(void)

- ea: `0x1400c9d34`
- end: `0x1400c9ef0`
- name: `?VidMmInitializeSystemResourcePool@@YAJXZ`
- size: `444`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140124808`

## callees

- `0x1400c9014`
- `0x1400c9488`
- `0x1400c999c`
- `0x1400c9c3c`
- `0x1400c9c8c`
- `0x1400c9d34`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400c9e89`
- `ntoskrnl!ObfDereferenceObject` at `0x1400c9ead`
- `ntoskrnl!ObfDereferenceObject` at `0x1400c9e89`
- `ntoskrnl!ObfDereferenceObject` at `0x1400c9ead`
- `ntoskrnl!ObCloseHandle` at `0x1400c9e72`
- `ntoskrnl!ObCloseHandle` at `0x1400c9e72`
- `ntoskrnl!ZwCreatePartition` at `0x1400c9db8`
- `ntoskrnl!ZwCreatePartition` at `0x1400c9db8`
- `watchdog!WdLogSingleEntry1` at `0x1400c9dce`
- `watchdog!WdLogSingleEntry1` at `0x1400c9dce`

## pseudocode

```c
__int64 VidMmInitializeSystemResourcePool(void)
{
  __int128 *v0; // rbx
  struct VIDMM_PARTITION *v1; // rdi
  struct VIDMM_PARTITION *v2; // r14
  int v3; // eax
  int Partition; // ebx
  int v5; // eax
  HANDLE Handle; // [rsp+28h] [rbp-48h] BYREF
  __int128 v8; // [rsp+30h] [rbp-40h] BYREF
  __int128 v9; // [rsp+40h] [rbp-30h] BYREF
  __int128 v10; // [rsp+50h] [rbp-20h]
  __int128 v11; // [rsp+60h] [rbp-10h]
  PVOID v12; // [rsp+A0h] [rbp+30h] BYREF
  struct VIDMM_PARTITION *v13; // [rsp+A8h] [rbp+38h]
  PVOID Object; // [rsp+B0h] [rbp+40h] BYREF
  struct VIDMM_PARTITION *v15; // [rsp+B8h] [rbp+48h]

  v0 = 0;
  v1 = 0;
  Object = 0;
  v2 = 0;
  v13 = 0;
  v12 = 0;
  v9 = 0;
  Handle = 0;
  v10 = 0;
  v15 = 0;
  v11 = 0;
  v8 = *(_OWORD *)L"XZ";
  if ( g_Feature_IntelligentCarveout )
  {
    LODWORD(v9) = 48;
    *(_QWORD *)&v10 = &v8;
    *((_QWORD *)&v9 + 1) = 0;
    DWORD2(v10) = 576;
    v11 = 0;
    v3 = ZwCreatePartition(0, &Handle, 2031619, &v9);
    if ( v3 >= 0 )
    {
      v0 = &v8;
    }
    else
    {
      WdLogSingleEntry1(3, v3);
      WdLogGlobalForLineNumber = 2008;
    }
  }
  Partition = OpenPartitionsByName(L">@", v0, &Object, &v12);
  if ( Partition >= 0 )
  {
    Partition = FindOrCreatePartition((struct _EPARTITION *)Object);
    if ( Partition < 0
      || v12 && (v5 = FindOrCreatePartition((struct _EPARTITION *)v12), v2 = v15, Partition = v5, v5 < 0) )
    {
      v1 = v13;
    }
    else
    {
      v1 = v13;
      Partition = CreateAndInitializeResourcePool(v13, v2);
      if ( Partition >= 0 )
      {
        g_pSystemResourcePool = 0;
        Partition = 0;
      }
    }
  }
  if ( Handle )
    ObCloseHandle(Handle, 0);
  if ( Object )
    ObfDereferenceObject(Object);
  if ( v1 )
    VidMmDereferencePartition(v1);
  if ( v12 )
    ObfDereferenceObject(v12);
  if ( v2 )
    VidMmDereferencePartition(v2);
  return (unsigned int)Partition;
}

```

## disassembly

```asm
0x1400c9d34  push    rbp
0x1400c9d36  push    rbx
0x1400c9d37  push    rsi
0x1400c9d38  push    rdi
0x1400c9d39  push    r14
0x1400c9d3b  mov     rbp, rsp
0x1400c9d3e  sub     rsp, 70h
0x1400c9d42  xorps   xmm0, xmm0
0x1400c9d45  xor     ebx, ebx
0x1400c9d47  xor     edi, edi
0x1400c9d49  mov     [rbp+Object], rbx
0x1400c9d4d  xor     r14d, r14d
0x1400c9d50  mov     [rbp+arg_8], rdi
0x1400c9d54  xor     esi, esi
0x1400c9d56  mov     [rbp+arg_0], rbx
0x1400c9d5a  cmp     cs:?g_Feature_IntelligentCarveout@@3_NA, bl; bool g_Feature_IntelligentCarveout
0x1400c9d60  movups  [rbp+var_30], xmm0
0x1400c9d64  mov     [rbp+Handle], rbx
0x1400c9d68  movups  [rbp+var_20], xmm0
0x1400c9d6c  mov     [rbp+arg_18], r14
0x1400c9d70  movups  [rbp+var_10], xmm0
0x1400c9d74  mov     [rbp+var_50], rsi
0x1400c9d78  movups  xmm0, xmmword ptr cs:aXz; "XZ"
0x1400c9d7f  movdqu  [rbp+var_40], xmm0
0x1400c9d84  jz      short loc_1400C9DEA
0x1400c9d86  lea     rax, [rbp+var_40]
0x1400c9d8a  mov     dword ptr [rbp+var_30], 30h ; '0'
0x1400c9d91  xorps   xmm0, xmm0
0x1400c9d94  mov     qword ptr [rbp+var_20], rax
0x1400c9d98  lea     r9, [rbp+var_30]
0x1400c9d9c  mov     qword ptr [rbp+var_30+8], rbx
0x1400c9da0  mov     r8d, 1F0003h
0x1400c9da6  mov     dword ptr [rbp+var_20+8], 240h
0x1400c9dad  lea     rdx, [rbp+Handle]
0x1400c9db1  xor     ecx, ecx
0x1400c9db3  movdqu  [rbp+var_10], xmm0
0x1400c9db8  call    cs:__imp_ZwCreatePartition
0x1400c9dbf  nop     dword ptr [rax+rax+00h]
0x1400c9dc4  test    eax, eax
0x1400c9dc6  jns     short loc_1400C9DE6
0x1400c9dc8  movsxd  rdx, eax
0x1400c9dcb  lea     ecx, [rbx+3]
0x1400c9dce  call    cs:__imp_WdLogSingleEntry1
0x1400c9dd5  nop     dword ptr [rax+rax+00h]
0x1400c9dda  mov     cs:WdLogGlobalForLineNumber, 7D8h
0x1400c9de4  jmp     short loc_1400C9DEA
0x1400c9de6  lea     rbx, [rbp+var_40]
0x1400c9dea  lea     r9, [rbp+arg_0]
0x1400c9dee  mov     rdx, rbx
0x1400c9df1  lea     r8, [rbp+Object]
0x1400c9df5  lea     rcx, asc_14005CA48; ">@"
0x1400c9dfc  call    OpenPartitionsByName
0x1400c9e01  mov     ebx, eax
0x1400c9e03  test    eax, eax
0x1400c9e05  js      short loc_1400C9E67
0x1400c9e07  mov     rcx, [rbp+Object]; struct _EPARTITION *
0x1400c9e0b  lea     r8, [rbp+arg_8]
0x1400c9e0f  xor     edx, edx
0x1400c9e11  call    FindOrCreatePartition
0x1400c9e16  mov     ebx, eax
0x1400c9e18  test    eax, eax
0x1400c9e1a  js      short loc_1400C9E63
0x1400c9e1c  cmp     [rbp+arg_0], rsi
0x1400c9e20  jz      short loc_1400C9E3B
0x1400c9e22  mov     rcx, [rbp+arg_0]; struct _EPARTITION *
0x1400c9e26  lea     r8, [rbp+arg_18]
0x1400c9e2a  xor     edx, edx
0x1400c9e2c  call    FindOrCreatePartition
0x1400c9e31  mov     r14, [rbp+arg_18]
0x1400c9e35  mov     ebx, eax
0x1400c9e37  test    eax, eax
0x1400c9e39  js      short loc_1400C9E63
0x1400c9e3b  mov     rdi, [rbp+arg_8]
0x1400c9e3f  lea     r8, [rbp+var_50]
0x1400c9e43  mov     rcx, rdi; struct VIDMM_PARTITION *
0x1400c9e46  mov     rdx, r14; struct VIDMM_PARTITION *
0x1400c9e49  call    CreateAndInitializeResourcePool
0x1400c9e4e  mov     rsi, [rbp+var_50]
0x1400c9e52  mov     ebx, eax
0x1400c9e54  test    eax, eax
0x1400c9e56  js      short loc_1400C9E67
0x1400c9e58  mov     cs:?g_pSystemResourcePool@@3PEAUVIDMM_RESOURCE_POOL@@EA, rsi; VIDMM_RESOURCE_POOL * g_pSystemResourcePool
0x1400c9e5f  xor     ebx, ebx
0x1400c9e61  jmp     short loc_1400C9E67
0x1400c9e63  mov     rdi, [rbp+arg_8]
0x1400c9e67  mov     rcx, [rbp+Handle]; Handle
0x1400c9e6b  test    rcx, rcx
0x1400c9e6e  jz      short loc_1400C9E7E
0x1400c9e70  xor     edx, edx; PreviousMode
0x1400c9e72  call    cs:__imp_ObCloseHandle
0x1400c9e79  nop     dword ptr [rax+rax+00h]
0x1400c9e7e  cmp     [rbp+Object], 0
0x1400c9e83  jz      short loc_1400C9E95
0x1400c9e85  mov     rcx, [rbp+Object]; Object
0x1400c9e89  call    cs:__imp_ObfDereferenceObject
0x1400c9e90  nop     dword ptr [rax+rax+00h]
0x1400c9e95  test    rdi, rdi
0x1400c9e98  jz      short loc_1400C9EA2
0x1400c9e9a  mov     rcx, rdi; this
0x1400c9e9d  call    ?VidMmDereferencePartition@@YAXPEBUVIDMM_PARTITION@@@Z; VidMmDereferencePartition(VIDMM_PARTITION const *)
0x1400c9ea2  cmp     [rbp+arg_0], 0
0x1400c9ea7  jz      short loc_1400C9EB9
0x1400c9ea9  mov     rcx, [rbp+arg_0]; Object
0x1400c9ead  call    cs:__imp_ObfDereferenceObject
0x1400c9eb4  nop     dword ptr [rax+rax+00h]
0x1400c9eb9  test    r14, r14
0x1400c9ebc  jz      short loc_1400C9EC6
0x1400c9ebe  mov     rcx, r14; this
0x1400c9ec1  call    ?VidMmDereferencePartition@@YAXPEBUVIDMM_PARTITION@@@Z; VidMmDereferencePartition(VIDMM_PARTITION const *)
0x1400c9ec6  test    ebx, ebx
0x1400c9ec8  jns     short loc_1400C9EE2
0x1400c9eca  test    rsi, rsi
0x1400c9ecd  jz      short loc_1400C9EE2
0x1400c9ecf  mov     rcx, rsi; this
0x1400c9ed2  call    ?VidMmDereferenceResourcePool@@YAXPEBUVIDMM_RESOURCE_POOL@@@Z; VidMmDereferenceResourcePool(VIDMM_RESOURCE_POOL const *)
0x1400c9ed7  mov     cs:?g_pSystemResourcePool@@3PEAUVIDMM_RESOURCE_POOL@@EA, 0; VIDMM_RESOURCE_POOL * g_pSystemResourcePool
0x1400c9ee2  mov     eax, ebx
0x1400c9ee4  add     rsp, 70h
0x1400c9ee8  pop     r14
0x1400c9eea  pop     rdi
0x1400c9eeb  pop     rsi
0x1400c9eec  pop     rbx
0x1400c9eed  pop     rbp
0x1400c9eee  retn
```
