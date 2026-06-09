# MountMgrCreatePoint

- ea: `0x14000bcac`
- end: `0x14000be46`
- name: `MountMgrCreatePoint`
- size: `410`
- prototype: `__int64 __fastcall(_QWORD *Context, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1400147a0`

## callees

- `0x140001ae0`
- `0x14000bcac`
- `0x14000be4c`
- `0x14000c2d4`
- `0x1400144a0`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x14000bde2`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000bde2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000be2c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000be2c`

## pseudocode

```c
__int64 __fastcall MountMgrCreatePoint(_QWORD *Context, __int64 a2)
{
  __int64 v2; // rax
  unsigned int v4; // r9d
  unsigned __int16 *v5; // rdx
  __int64 v6; // r11
  __int64 v7; // r8
  int v8; // r10d
  unsigned int v9; // ecx
  int v10; // ebx
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  __int64 v14; // rcx
  const UNICODE_STRING *i; // rbx
  int PointWorker; // eax
  __int128 v18; // [rsp+20h] [rbp-30h] BYREF
  struct _UNICODE_STRING ObjectName; // [rsp+30h] [rbp-20h] BYREF
  UNICODE_STRING String1; // [rsp+40h] [rbp-10h] BYREF

  v2 = *(_QWORD *)(a2 + 184);
  ObjectName = 0;
  String1 = 0;
  v4 = *(_DWORD *)(v2 + 16);
  v18 = 0;
  if ( v4 < 8 )
    goto LABEL_23;
  v5 = *(unsigned __int16 **)(a2 + 24);
  v6 = *v5;
  v7 = v5[1];
  v8 = v5[3];
  v9 = v8 + v5[2];
  if ( v9 <= (int)v7 + (int)v6 )
    v9 = v7 + v6;
  if ( v9 > v4 )
  {
    v10 = -1073741811;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v12 = 201;
      v13 = 3221225485LL;
LABEL_9:
      WPP_SF_L(v11->AttachedDevice, v12, v7, v13);
      goto LABEL_24;
    }
    goto LABEL_24;
  }
  WORD1(v18) = v5[1];
  *((_QWORD *)&v18 + 1) = (char *)v5 + v6;
  LOWORD(v18) = v7;
  if ( (unsigned int)v7 < 2 || !*(unsigned __int16 *)((char *)v5 + v6) )
  {
LABEL_23:
    v10 = -1073741811;
    goto LABEL_24;
  }
  ObjectName.MaximumLength = v8;
  ObjectName.Length = v8;
  ObjectName.Buffer = (unsigned __int16 *)((char *)v5 + v5[2]);
  v10 = QueryDeviceName(&ObjectName, &String1);
  if ( v10 >= 0 )
  {
    for ( i = (const UNICODE_STRING *)Context[2]; ; i = *(const UNICODE_STRING **)&i->Length )
    {
      if ( i == (const UNICODE_STRING *)(Context + 2) )
      {
        PointWorker = MountMgrCreatePointWorkerLegacy(v14, &v18, &String1);
        goto LABEL_21;
      }
      if ( !RtlCompareUnicodeString(&String1, i + 5, 1u) )
        break;
    }
    PointWorker = MountMgrCreatePointWorker(Context);
LABEL_21:
    v10 = PointWorker;
  }
  else
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v12 = 202;
      v13 = (unsigned int)v10;
      goto LABEL_9;
    }
  }
LABEL_24:
  if ( String1.Buffer )
    ExFreePoolWithTag(String1.Buffer, 0);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14000bcac  push    rbp
0x14000bcae  push    rbx
0x14000bcaf  push    rsi
0x14000bcb0  push    rdi
0x14000bcb1  push    r14
0x14000bcb3  mov     rbp, rsp
0x14000bcb6  sub     rsp, 50h
0x14000bcba  mov     rax, [rdx+0B8h]
0x14000bcc1  xorps   xmm0, xmm0
0x14000bcc4  xorps   xmm1, xmm1
0x14000bcc7  xor     r14d, r14d
0x14000bcca  movups  xmmword ptr [rbp+ObjectName.Length], xmm1
0x14000bcce  mov     rsi, rcx
0x14000bcd1  movups  xmmword ptr [rbp+String1.Length], xmm0
0x14000bcd5  mov     r9d, [rax+10h]
0x14000bcd9  movups  [rbp+var_30], xmm0
0x14000bcdd  cmp     r9d, 8
0x14000bce1  jb      loc_14000BE1C
0x14000bce7  mov     rdx, [rdx+18h]
0x14000bceb  movzx   r11d, word ptr [rdx]
0x14000bcef  movzx   r8d, word ptr [rdx+2]
0x14000bcf4  movzx   r10d, word ptr [rdx+6]
0x14000bcf9  movzx   ecx, word ptr [rdx+4]
0x14000bcfd  add     ecx, r10d
0x14000bd00  lea     eax, [r8+r11]
0x14000bd04  cmp     ecx, eax
0x14000bd06  cmovbe  ecx, eax
0x14000bd09  cmp     ecx, r9d
0x14000bd0c  jbe     short loc_14000BD58
0x14000bd0e  mov     ebx, 0C000000Dh
0x14000bd13  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bd1a  lea     rax, WPP_GLOBAL_Control
0x14000bd21  cmp     rcx, rax
0x14000bd24  jz      loc_14000BE21
0x14000bd2a  mov     eax, [rcx+2Ch]
0x14000bd2d  test    al, 1
0x14000bd2f  jz      loc_14000BE21
0x14000bd35  cmp     byte ptr [rcx+29h], 2
0x14000bd39  jb      loc_14000BE21
0x14000bd3f  mov     edx, 0C9h
0x14000bd44  mov     r9d, 0C000000Dh
0x14000bd4a  mov     rcx, [rcx+18h]
0x14000bd4e  call    WPP_SF_L
0x14000bd53  jmp     loc_14000BE21
0x14000bd58  mov     word ptr [rbp+var_30+2], r8w
0x14000bd5d  lea     rax, [rdx+r11]
0x14000bd61  mov     qword ptr [rbp+var_30+8], rax
0x14000bd65  mov     word ptr [rbp+var_30], r8w
0x14000bd6a  cmp     r8d, 2
0x14000bd6e  jb      loc_14000BE1C
0x14000bd74  cmp     [rax], r14w
0x14000bd78  jz      loc_14000BE1C
0x14000bd7e  mov     [rbp+ObjectName.MaximumLength], r10w
0x14000bd83  lea     rcx, [rbp+ObjectName]; ObjectName
0x14000bd87  mov     [rbp+ObjectName.Length], r10w
0x14000bd8c  movzx   eax, word ptr [rdx+4]
0x14000bd90  add     rax, rdx
0x14000bd93  lea     rdx, [rbp+String1]; StringOut
0x14000bd97  mov     [rbp+ObjectName.Buffer], rax
0x14000bd9b  call    QueryDeviceName
0x14000bda0  mov     ebx, eax
0x14000bda2  test    eax, eax
0x14000bda4  jns     short loc_14000BDCE
0x14000bda6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bdad  lea     rax, WPP_GLOBAL_Control
0x14000bdb4  cmp     rcx, rax
0x14000bdb7  jz      short loc_14000BE21
0x14000bdb9  mov     edx, [rcx+2Ch]
0x14000bdbc  test    dl, 1
0x14000bdbf  jz      short loc_14000BE21
0x14000bdc1  mov     edx, 0CAh
0x14000bdc6  mov     r9d, ebx
0x14000bdc9  jmp     loc_14000BD4A
0x14000bdce  lea     rdi, [rsi+10h]
0x14000bdd2  mov     rbx, [rdi]
0x14000bdd5  jmp     short loc_14000BDF5
0x14000bdd7  lea     rdx, [rbx+50h]; String2
0x14000bddb  mov     r8b, 1; CaseInSensitive
0x14000bdde  lea     rcx, [rbp+String1]; String1
0x14000bde2  call    cs:__imp_RtlCompareUnicodeString
0x14000bde9  nop     dword ptr [rax+rax+00h]
0x14000bdee  test    eax, eax
0x14000bdf0  jz      short loc_14000BE0B
0x14000bdf2  mov     rbx, [rbx]
0x14000bdf5  cmp     rbx, rdi
0x14000bdf8  jnz     short loc_14000BDD7
0x14000bdfa  lea     r8, [rbp+String1]
0x14000bdfe  lea     rdx, [rbp+var_30]
0x14000be02  call    MountMgrCreatePointWorkerLegacy
0x14000be07  mov     ebx, eax
0x14000be09  jmp     short loc_14000BE21
0x14000be0b  mov     r8, rbx
0x14000be0e  lea     rdx, [rbp+var_30]
0x14000be12  mov     rcx, rsi; Context
0x14000be15  call    MountMgrCreatePointWorker
0x14000be1a  jmp     short loc_14000BE07
0x14000be1c  mov     ebx, 0C000000Dh
0x14000be21  mov     rcx, [rbp+String1.Buffer]; P
0x14000be25  test    rcx, rcx
0x14000be28  jz      short loc_14000BE38
0x14000be2a  xor     edx, edx; Tag
0x14000be2c  call    cs:__imp_ExFreePoolWithTag
0x14000be33  nop     dword ptr [rax+rax+00h]
0x14000be38  mov     eax, ebx
0x14000be3a  add     rsp, 50h
0x14000be3e  pop     r14
0x14000be40  pop     rdi
0x14000be41  pop     rsi
0x14000be42  pop     rbx
0x14000be43  pop     rbp
0x14000be44  retn
```
