# SecCreateInstanceContext

- ea: `0x1400234ec`
- end: `0x1400237d9`
- name: `SecCreateInstanceContext`
- size: `749`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x14002a0f0`

## callees

- `0x140010347`
- `0x14001039b`
- `0x1400103b3`
- `0x1400103bf`
- `0x14001041f`
- `0x14001042b`
- `0x140011610`
- `0x140011650`
- `0x1400119c0`
- `0x1400234ec`
- `0x140023cc8`
- `0x14002aa18`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002366e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002366e`
- `ntoskrnl!KeInitializeEvent` at `0x140023629`
- `ntoskrnl!KeInitializeEvent` at `0x140023629`

## pseudocode

```c
NTSTATUS __fastcall SecCreateInstanceContext(PFLT_FILTER *a1, unsigned int a2, int a3)
{
  NTSTATUS result; // eax
  _QWORD *v7; // rax
  struct _KEVENT *v8; // rcx
  ULONG v9; // eax
  SIZE_T v10; // rdx
  PVOID PoolWithTag; // rax
  NTSTATUS VolumeName_0; // ebx
  PFLT_CONTEXT v13; // r8
  _QWORD *v14; // rcx
  char *v15; // rax
  PVOID *v16; // rdx
  PFLT_CONTEXT NewContext; // [rsp+40h] [rbp-38h] BYREF
  ULONG v18; // [rsp+48h] [rbp-30h] BYREF
  __int128 v19; // [rsp+50h] [rbp-28h] BYREF

  NewContext = 0;
  v18 = 0;
  if ( FltGetVolumeName_0(a1[2], 0, &v18) != -1073741789 )
    return -1073741808;
  result = FltAllocateContext_0(
             a1[1],
             2u,
             0x80u,
             (POOL_TYPE)((((unsigned int)dword_140020004 >> 2) & 1) << 9),
             &NewContext);
  if ( result < 0 )
  {
    _mm_lfence();
    return result;
  }
  memset(NewContext, 0, 0x80u);
  *(_WORD *)NewContext = -5631;
  *((_WORD *)NewContext + 1) = 128;
  *((_QWORD *)NewContext + 6) = a1[3];
  *((_QWORD *)NewContext + 7) = a1[2];
  *((_DWORD *)NewContext + 17) = a2;
  *((_DWORD *)NewContext + 16) = a3;
  v7 = (char *)NewContext + 8;
  *((_QWORD *)NewContext + 2) = (char *)NewContext + 8;
  *v7 = v7;
  v8 = (struct _KEVENT *)NewContext;
  *((_DWORD *)NewContext + 18) = 1;
  v8[3].Header.WaitListHead.Flink = 0;
  LODWORD(v8[3].Header.WaitListHead.Blink) = 0;
  KeInitializeEvent(v8 + 4, SynchronizationEvent, 0);
  v9 = v18;
  if ( !v18 )
    goto LABEL_16;
  v18 += 2;
  v10 = v9 + 2;
  if ( qword_140020008 )
    PoolWithTag = (PVOID)qword_140020008(256, v10, 1853252435);
  else
    PoolWithTag = ExAllocatePoolWithTag(PagedPool, v10, 0x6E766353u);
  *((_QWORD *)NewContext + 4) = PoolWithTag;
  if ( *((_QWORD *)NewContext + 4) )
  {
    if ( v18 > 0xFFFF )
    {
      *((_WORD *)NewContext + 13) = -1;
      VolumeName_0 = -1073741675;
    }
    else
    {
      *((_WORD *)NewContext + 13) = v18;
      VolumeName_0 = 0;
    }
    if ( VolumeName_0 < 0 )
      goto LABEL_23;
    VolumeName_0 = FltGetVolumeName_0(a1[2], (PUNICODE_STRING)((char *)NewContext + 24), 0);
    if ( VolumeName_0 < 0 )
      goto LABEL_23;
LABEL_16:
    SecSetVolumeProperties(a1, a2, NewContext);
    v13 = NewContext;
    if ( (*((_DWORD *)NewContext + 10) & 1) != 0 && !*((_QWORD *)SecData + 145) )
    {
      v19 = 0;
      SecAppendUnicodeStringToUnicodeString((char *)NewContext + 24, &v19, (char *)SecData + 1160, 1853252435);
      v13 = NewContext;
    }
    VolumeName_0 = FltSetInstanceContext_0(a1[3], FLT_SET_CONTEXT_KEEP_IF_EXISTS, v13, 0);
    if ( VolumeName_0 >= 0 )
    {
      FltAcquirePushLockExclusiveEx_0((char *)SecData + 328, 0);
      v14 = (char *)NewContext + 8;
      v15 = (char *)SecData + 304;
      v16 = (PVOID *)*((_QWORD *)SecData + 39);
      if ( *v16 != (char *)SecData + 304 )
        __fastfail(3u);
      *v14 = v15;
      v14[1] = v16;
      *v16 = v14;
      *((_QWORD *)v15 + 1) = v14;
      FltReleasePushLockEx_0((char *)SecData + 328, 0);
    }
    goto LABEL_23;
  }
  VolumeName_0 = -1073741670;
LABEL_23:
  FltReleaseContext_0(NewContext);
  return VolumeName_0;
}

```

## disassembly

```asm
0x1400234ec  mov     r11, rsp
0x1400234ef  mov     [r11+10h], rbx
0x1400234f3  mov     [r11+18h], rsi
0x1400234f7  mov     [r11+20h], rdi
0x1400234fb  push    r12
0x1400234fd  sub     rsp, 70h
0x140023501  mov     rax, cs:__security_cookie
0x140023508  xor     rax, rsp
0x14002350b  mov     [rsp+78h+var_18], rax
0x140023510  mov     ebx, r8d
0x140023513  mov     esi, edx
0x140023515  mov     rdi, rcx
0x140023518  mov     qword ptr [r11-38h], 0
0x140023520  mov     [rsp+78h+var_30], 0
0x140023528  lea     r8, [r11-30h]; BufferSizeNeeded
0x14002352c  xor     edx, edx; VolumeName
0x14002352e  mov     rcx, [rcx+10h]; Volume
0x140023532  call    FltGetVolumeName_0
0x140023537  cmp     eax, 0C0000023h
0x14002353c  jz      short loc_140023568
0x14002353e  mov     eax, 0C0000010h
0x140023543  mov     rcx, [rsp+78h+var_18]
0x140023548  xor     rcx, rsp; StackCookie
0x14002354b  call    __security_check_cookie
0x140023550  lea     r11, [rsp+78h+var_8]
0x140023555  mov     rbx, [r11+18h]
0x140023559  mov     rsi, [r11+20h]
0x14002355d  mov     rdi, [r11+28h]
0x140023561  mov     rsp, r11
0x140023564  pop     r12
0x140023566  retn
0x140023568  mov     r9d, cs:dword_140020004
0x14002356f  shr     r9d, 2
0x140023573  and     r9d, 1
0x140023577  shl     r9d, 9; PoolType
0x14002357b  mov     edx, 2; ContextType
0x140023580  lea     rax, [rsp+78h+NewContext]
0x140023585  mov     [rsp+78h+ReturnedContext], rax; ReturnedContext
0x14002358a  lea     r12d, [rdx+7Eh]
0x14002358e  mov     r8d, r12d; ContextSize
0x140023591  mov     rcx, [rdi+8]; Filter
0x140023595  call    FltAllocateContext_0
0x14002359a  test    eax, eax
0x14002359c  jns     short loc_1400235A3
0x14002359e  lfence
0x1400235a1  jmp     short loc_140023543
0x1400235a3  mov     r8, r12; Size
0x1400235a6  xor     edx, edx; Val
0x1400235a8  mov     rcx, [rsp+78h+NewContext]; void *
0x1400235ad  call    memset
0x1400235b2  mov     ecx, 0EA01h
0x1400235b7  mov     rax, [rsp+78h+NewContext]
0x1400235bc  mov     [rax], cx
0x1400235bf  mov     rax, [rsp+78h+NewContext]
0x1400235c4  mov     [rax+2], r12w
0x1400235c9  mov     rcx, [rdi+18h]
0x1400235cd  mov     rax, [rsp+78h+NewContext]
0x1400235d2  mov     [rax+30h], rcx
0x1400235d6  mov     rcx, [rdi+10h]
0x1400235da  mov     rax, [rsp+78h+NewContext]
0x1400235df  mov     [rax+38h], rcx
0x1400235e3  mov     rax, [rsp+78h+NewContext]
0x1400235e8  mov     [rax+44h], esi
0x1400235eb  mov     rax, [rsp+78h+NewContext]
0x1400235f0  mov     [rax+40h], ebx
0x1400235f3  mov     rax, [rsp+78h+NewContext]
0x1400235f8  add     rax, 8
0x1400235fc  mov     [rax+8], rax
0x140023600  mov     [rax], rax
0x140023603  mov     rcx, [rsp+78h+NewContext]
0x140023608  mov     dword ptr [rcx+48h], 1
0x14002360f  mov     qword ptr [rcx+50h], 0
0x140023617  mov     dword ptr [rcx+58h], 0
0x14002361e  add     rcx, 60h ; '`'; Event
0x140023622  xor     r8d, r8d; State
0x140023625  lea     edx, [r8+1]; Type
0x140023629  call    cs:__imp_KeInitializeEvent
0x140023630  nop     dword ptr [rax+rax+00h]
0x140023635  mov     eax, [rsp+78h+var_30]
0x140023639  test    eax, eax
0x14002363b  jz      loc_1400236F6
0x140023641  add     eax, 2
0x140023644  mov     [rsp+78h+var_30], eax
0x140023648  mov     edx, eax; NumberOfBytes
0x14002364a  mov     rax, cs:qword_140020008
0x140023651  mov     r8d, 6E766353h; Tag
0x140023657  test    rax, rax
0x14002365a  jz      short loc_140023669
0x14002365c  mov     ecx, 100h
0x140023661  call    cs:__guard_dispatch_icall_fptr
0x140023667  jmp     short loc_14002367A
0x140023669  mov     ecx, 1; PoolType
0x14002366e  call    cs:__imp_ExAllocatePoolWithTag
0x140023675  nop     dword ptr [rax+rax+00h]
0x14002367a  mov     rcx, rax
0x14002367d  mov     rax, [rsp+78h+NewContext]
0x140023682  mov     [rax+20h], rcx
0x140023686  mov     rax, [rsp+78h+NewContext]
0x14002368b  cmp     qword ptr [rax+20h], 0
0x140023690  jnz     short loc_1400236A0
0x140023692  mov     ebx, 0C000009Ah
0x140023697  mov     [rsp+78h+var_48], ebx
0x14002369b  jmp     loc_1400237C8
0x1400236a0  mov     rcx, [rsp+78h+NewContext]
0x1400236a5  mov     eax, [rsp+78h+var_30]
0x1400236a9  mov     [rsp+78h+var_40], eax
0x1400236ad  mov     edx, 0FFFFh
0x1400236b2  cmp     eax, edx
0x1400236b4  ja      short loc_1400236BE
0x1400236b6  mov     [rcx+1Ah], ax
0x1400236ba  xor     ebx, ebx
0x1400236bc  jmp     short loc_1400236C7
0x1400236be  mov     [rcx+1Ah], dx
0x1400236c2  mov     ebx, 0C0000095h
0x1400236c7  mov     [rsp+78h+var_48], ebx
0x1400236cb  test    ebx, ebx
0x1400236cd  js      loc_1400237C8
0x1400236d3  mov     rdx, [rsp+78h+NewContext]
0x1400236d8  add     rdx, 18h; VolumeName
0x1400236dc  xor     r8d, r8d; BufferSizeNeeded
0x1400236df  mov     rcx, [rdi+10h]; Volume
0x1400236e3  call    FltGetVolumeName_0
0x1400236e8  mov     ebx, eax
0x1400236ea  mov     [rsp+78h+var_48], eax
0x1400236ee  test    eax, eax
0x1400236f0  js      loc_1400237C8
0x1400236f6  mov     r8, [rsp+78h+NewContext]
0x1400236fb  mov     edx, esi
0x1400236fd  mov     rcx, rdi
0x140023700  call    SecSetVolumeProperties
0x140023705  mov     r8, [rsp+78h+NewContext]
0x14002370a  mov     eax, [r8+28h]
0x14002370e  test    al, 1
0x140023710  jz      short loc_14002374F
0x140023712  mov     rax, cs:SecData
0x140023719  cmp     qword ptr [rax+488h], 0
0x140023721  jnz     short loc_14002374F
0x140023723  xorps   xmm0, xmm0
0x140023726  movups  [rsp+78h+var_28], xmm0
0x14002372b  lea     rcx, [r8+18h]
0x14002372f  mov     r9d, 6E766353h
0x140023735  lea     r8, [rax+488h]
0x14002373c  lea     rdx, [rsp+78h+var_28]
0x140023741  call    SecAppendUnicodeStringToUnicodeString
0x140023746  mov     [rsp+78h+var_48], eax
0x14002374a  mov     r8, [rsp+78h+NewContext]; NewContext
0x14002374f  xor     r9d, r9d; OldContext
0x140023752  lea     edx, [r9+1]; Operation
0x140023756  mov     rcx, [rdi+18h]; Instance
0x14002375a  call    FltSetInstanceContext_0
0x14002375f  mov     ebx, eax
0x140023761  mov     [rsp+78h+var_48], eax
0x140023765  test    eax, eax
0x140023767  js      short loc_1400237C8
0x140023769  mov     rcx, cs:SecData
0x140023770  add     rcx, 148h
0x140023777  xor     edx, edx
0x140023779  call    FltAcquirePushLockExclusiveEx_0
0x14002377e  mov     rcx, [rsp+78h+NewContext]
0x140023783  add     rcx, 8
0x140023787  mov     rax, cs:SecData
0x14002378e  add     rax, 130h
0x140023794  mov     rdx, [rax+8]
0x140023798  cmp     [rdx], rax
0x14002379b  jz      short loc_1400237A4
0x14002379d  mov     ecx, 3
0x1400237a2  int     29h; Win8: RtlFailFast(ecx)
0x1400237a4  mov     [rcx], rax
0x1400237a7  mov     [rcx+8], rdx
0x1400237ab  mov     [rdx], rcx
0x1400237ae  mov     [rax+8], rcx
0x1400237b2  mov     rcx, cs:SecData
0x1400237b9  add     rcx, 148h
0x1400237c0  xor     edx, edx
0x1400237c2  call    FltReleasePushLockEx_0
0x1400237c7  nop
0x1400237c8  mov     rcx, [rsp+78h+NewContext]; Context
0x1400237cd  call    FltReleaseContext_0
0x1400237d2  mov     eax, ebx
0x1400237d4  jmp     loc_140023543
0x140044506  push    rbp
0x140044508  sub     rsp, 30h
0x14004450c  mov     rbp, rdx
0x14004450f  mov     rcx, [rbp+40h]; Context
0x140044513  call    FltReleaseContext_0
0x140044518  nop
0x140044519  add     rsp, 30h
0x14004451d  pop     rbp
0x14004451e  retn
```
