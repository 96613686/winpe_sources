# CClfsBaseFile::ScanContainerInfo(ulong const * const,_CLS_LSN const &,_CLS_LSN const &,_CLS_LSN const &,ulong,uchar,_CLS_CONTAINER_INFORMATION *,char,ulong &,ulong &)

- ea: `0x140063dcc`
- end: `0x140064372`
- name: `?ScanContainerInfo@CClfsBaseFile@@QEAAJQEBKAEBT_CLS_LSN@@11KEPEAU_CLS_CONTAINER_INFORMATION@@DAEAK3@Z`
- size: `1446`
- prototype: `__int64 __usercall@<rax>(CClfsBaseFile *__hidden this@<rcx>, const unsigned int *const@<rdx>, const union _CLS_LSN *@<r8>, const union _CLS_LSN *@<r9>, CLFS_LSN *, unsigned int, char, struct _CLS_CONTAINER_INFORMATION *, char, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400343e0`

## callees

- `0x140003590`
- `0x14000b6b0`
- `0x140038b18`
- `0x14003ea10`
- `0x140061e00`
- `0x140062c20`
- `0x140062df0`
- `0x140063dcc`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140063e59`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140063e59`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14006409d`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14006429b`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14006409d`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14006429b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400640e7`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400642e5`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400640e7`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400642e5`
- `ntoskrnl!RtlInitUnicodeString` at `0x14006406f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14006426d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14006406f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14006426d`

## pseudocode

```c
__int64 __fastcall CClfsBaseFile::ScanContainerInfo(
        PERESOURCE *this,
        const unsigned int *const a2,
        const union _CLS_LSN *a3,
        const union _CLS_LSN *a4,
        CLFS_LSN *a5,
        unsigned int a6,
        char a7,
        struct _CLS_CONTAINER_INFORMATION *a8,
        char a9,
        unsigned int *a10,
        unsigned int *a11)
{
  int Symbol; // esi
  unsigned int v14; // r15d
  unsigned int v15; // r12d
  struct _CLFS_BASE_RECORD_HEADER *BaseLogRecord; // rdx
  BOOLEAN v17; // r8
  CClfsBaseFile *v18; // rbx
  __int64 v19; // r13
  int v20; // edx
  struct _CLFS_CONTAINER_CONTEXT *v21; // r15
  CLFS_CONTAINER_STATE v22; // edx
  struct _CLS_CONTAINER_INFORMATION *v23; // rbx
  CLFS_CONTAINER_ID v24; // edi
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  __int64 v27; // r15
  int v28; // edx
  struct _CLFS_CONTAINER_CONTEXT *v29; // rcx
  CLFS_CONTAINER_STATE v30; // edx
  struct _CLS_CONTAINER_INFORMATION *v31; // rbx
  unsigned int v32; // edi
  BOOLEAN v34; // [rsp+20h] [rbp-B8h]
  UNICODE_STRING String2; // [rsp+30h] [rbp-A8h] BYREF
  int v36; // [rsp+40h] [rbp-98h]
  UNICODE_STRING DestinationString; // [rsp+48h] [rbp-90h] BYREF
  UNICODE_STRING v38; // [rsp+58h] [rbp-80h] BYREF
  unsigned int v39; // [rsp+68h] [rbp-70h]
  struct _UNICODE_STRING v40; // [rsp+70h] [rbp-68h] BYREF
  struct _CLFS_CONTAINER_CONTEXT *v41; // [rsp+80h] [rbp-58h] BYREF
  unsigned int v42; // [rsp+88h] [rbp-50h]
  struct _CLFS_BASE_RECORD_HEADER *v43; // [rsp+90h] [rbp-48h]
  unsigned int v48; // [rsp+128h] [rbp+50h]

  *(_QWORD *)&v38.Length = 0;
  v38.Buffer = 0;
  *(_QWORD *)&v40.Length = 0;
  v40.Buffer = 0;
  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = 0;
  *(_QWORD *)&String2.Length = 0;
  String2.Buffer = 0;
  v41 = 0;
  Symbol = 0;
  v48 = *a10;
  v14 = CClfsBaseFile::ContainerCount((CClfsBaseFile *)this);
  v39 = v14;
  v15 = 0;
  *a10 = 0;
  *a11 = 0;
  v34 = ExAcquireResourceSharedLite(this[4], 1u);
  BaseLogRecord = CClfsBaseFile::GetBaseLogRecord((CClfsBaseFile *)this);
  v43 = BaseLogRecord;
  if ( BaseLogRecord )
  {
    *a10 = 0;
    if ( (a7 & 2) != 0 )
    {
      while ( v15 < v14 )
      {
        if ( *a10 >= v48 )
          break;
        if ( v15 >= 0x400 )
          break;
        v19 = a2[((_WORD)a6 + (unsigned __int16)*a10) & 0x3FF];
        if ( (_DWORD)v19 == -1 )
          break;
        v20 = *((_DWORD *)BaseLogRecord + v19 + 202);
        if ( v20 )
        {
          v18 = (CClfsBaseFile *)this;
          Symbol = CClfsBaseFile::GetSymbol((CClfsBaseFile *)this, v20, v19, &v41);
          v36 = Symbol;
          if ( Symbol < 0 )
            goto LABEL_50;
          v21 = v41;
          v22 = *((_DWORD *)v41 + 9);
          if ( (v22 & 1) == 0 )
          {
            v23 = &a8[*a10];
            v23->State = v22;
            v23->PhysicalContainerId = *((_DWORD *)v21 + 4);
            v23->LogicalContainerId = *((_DWORD *)v21 + 5);
            if ( (*((_DWORD *)v21 + 9) & 0x38) == 0 )
            {
              v24 = *((_DWORD *)v21 + 5);
              if ( (v24 >= ClfsLsnContainer(a4) || a4 && CLFS_LSN_INVALID.ullOffset == a4->ullOffset)
                && v24 <= ClfsLsnContainer(a3) )
              {
                v23->State = 4;
              }
              else if ( ClfsLsnContainer(a5) > v24 || ClfsLsnContainer(a5) < v24 )
              {
                v23->State = 2;
              }
              else
              {
                v23->State = 16;
              }
            }
            CClfsAuthContainer::QueryContainerInfo(*((CClfsAuthContainer **)v21 + 3), v23);
            Symbol = CClfsBaseFile::GetContainerName((CClfsBaseFile *)this, v19, &v40);
            v36 = Symbol;
            if ( Symbol < 0 )
              goto LABEL_49;
            v23->FileNameActualLength = v40.Length;
            v23->FileNameLength = 510;
            if ( v40.Length < 0x1FEu )
              v23->FileNameLength = v40.Length;
            v38.Buffer = v23->FileName;
            *(_DWORD *)&v38.Length = 33423360;
            RtlInitUnicodeString(&DestinationString, L"\\??\\");
            String2 = v40;
            if ( a9 == 1 && RtlPrefixUnicodeString(&DestinationString, &String2, 0) )
            {
              String2.Buffer += (unsigned __int64)DestinationString.Length >> 1;
              String2.Length -= DestinationString.Length;
              String2.MaximumLength -= DestinationString.Length;
              v23->FileNameLength -= DestinationString.Length;
              v23->FileNameActualLength -= DestinationString.Length;
            }
            RtlCopyUnicodeString(&v38, &String2);
            v23->FileNameLength >>= 1;
            v23->FileNameActualLength >>= 1;
            ++*a10;
          }
        }
        v42 = ++v15;
        BaseLogRecord = v43;
        v14 = v39;
      }
      v25 = *a10 + a6;
      *a11 = v25;
      if ( v25 == -1 )
        *a11 = -2;
    }
    else
    {
      while ( v15 < v14 )
      {
        v26 = *a10;
        if ( *a10 >= v48 )
          break;
        if ( v15 >= 0x400 )
          break;
        if ( (int)(a6 - v26) < 0 )
          break;
        v27 = a2[((_WORD)a6 - (_WORD)v26) & 0x3FF];
        if ( (_DWORD)v27 == -1 )
          break;
        v28 = *((_DWORD *)BaseLogRecord + v27 + 202);
        if ( v28 )
        {
          Symbol = CClfsBaseFile::GetSymbol((CClfsBaseFile *)this, v28, v27, &v41);
          v36 = Symbol;
          v29 = v41;
          if ( !v41 )
            goto LABEL_49;
          v30 = *((_DWORD *)v41 + 9);
          if ( (v30 & 1) == 0 )
          {
            v31 = &a8[*a10];
            v31->State = v30;
            v31->PhysicalContainerId = *((_DWORD *)v29 + 4);
            v31->LogicalContainerId = *((_DWORD *)v29 + 5);
            CClfsAuthContainer::QueryContainerInfo(*((CClfsAuthContainer **)v29 + 3), v31);
            Symbol = CClfsBaseFile::GetContainerName((CClfsBaseFile *)this, v27, &v40);
            v36 = Symbol;
            if ( Symbol < 0 )
              goto LABEL_49;
            v31->FileNameActualLength = v40.Length;
            v31->FileNameLength = 510;
            if ( v40.Length < 0x1FEu )
              v31->FileNameLength = v40.Length;
            v38.Buffer = v31->FileName;
            *(_DWORD *)&v38.Length = 33423360;
            RtlInitUnicodeString(&DestinationString, L"\\??\\");
            String2 = v40;
            if ( a9 == 1 && RtlPrefixUnicodeString(&DestinationString, &String2, 0) )
            {
              String2.Buffer += (unsigned __int64)DestinationString.Length >> 1;
              String2.Length -= DestinationString.Length;
              String2.MaximumLength -= DestinationString.Length;
              v31->FileNameLength -= DestinationString.Length;
              v31->FileNameActualLength -= DestinationString.Length;
            }
            RtlCopyUnicodeString(&v38, &String2);
            v38.Buffer[(unsigned __int64)v38.Length >> 1] = 0;
            v31->FileNameLength >>= 1;
            v31->FileNameActualLength >>= 1;
            ++*a10;
          }
        }
        v42 = ++v15;
        BaseLogRecord = v43;
        v14 = v39;
      }
      v32 = a6 - *a10;
      *a11 = v32;
      if ( v32 == -1 )
        *a11 = 0;
    }
LABEL_49:
    v18 = (CClfsBaseFile *)this;
LABEL_50:
    v17 = v34;
  }
  else
  {
    Symbol = -1072037875;
    v36 = -1072037875;
    v18 = (CClfsBaseFile *)this;
  }
  if ( v17 )
    CClfsBaseFile::UnlockImage(v18);
  return (unsigned int)Symbol;
}

```

## disassembly

```asm
0x140063dcc  mov     r11, rsp
0x140063dcf  mov     [r11+20h], r9
0x140063dd3  mov     [r11+18h], r8
0x140063dd7  mov     [r11+10h], rdx
0x140063ddb  mov     [r11+8], rcx
0x140063ddf  push    rbx
0x140063de0  push    rsi
0x140063de1  push    rdi
0x140063de2  push    r12
0x140063de4  push    r13
0x140063de6  push    r14
0x140063de8  push    r15
0x140063dea  sub     rsp, 0A0h
0x140063df1  mov     r13, rcx
0x140063df4  xor     eax, eax
0x140063df6  mov     [r11-80h], rax
0x140063dfa  mov     [r11-78h], rax
0x140063dfe  mov     [r11-68h], rax
0x140063e02  mov     [r11-60h], rax
0x140063e06  mov     qword ptr [rsp+0D8h+DestinationString.Length], rax
0x140063e0b  mov     [rsp+0D8h+DestinationString.Buffer], rax
0x140063e10  mov     qword ptr [rsp+0D8h+String2.Length], rax
0x140063e15  mov     [rsp+0D8h+String2.Buffer], rax
0x140063e1a  mov     [r11-58h], rax
0x140063e1e  xor     esi, esi
0x140063e20  mov     r14, [rsp+0D8h+arg_48]
0x140063e28  mov     eax, [r14]
0x140063e2b  mov     dword ptr [rsp+0D8h+arg_48], eax
0x140063e32  call    ?ContainerCount@CClfsBaseFile@@QEAAKXZ; CClfsBaseFile::ContainerCount(void)
0x140063e37  mov     r15d, eax
0x140063e3a  mov     [rsp+0D8h+var_70], eax
0x140063e3e  xor     r12d, r12d
0x140063e41  mov     [rsp+0D8h+var_B8], sil
0x140063e46  mov     [r14], esi
0x140063e49  mov     rbx, [rsp+0D8h+arg_50]
0x140063e51  mov     [rbx], esi
0x140063e53  mov     dl, 1; Wait
0x140063e55  mov     rcx, [r13+20h]; Resource
0x140063e59  call    cs:__imp_ExAcquireResourceSharedLite
0x140063e60  nop     dword ptr [rax+rax+00h]
0x140063e65  mov     r8b, al
0x140063e68  mov     [rsp+0D8h+var_B8], al
0x140063e6c  mov     rcx, r13; this
0x140063e6f  call    ?GetBaseLogRecord@CClfsBaseFile@@IEAAPEAU_CLFS_BASE_RECORD_HEADER@@XZ; CClfsBaseFile::GetBaseLogRecord(void)
0x140063e74  mov     rdx, rax
0x140063e77  mov     [rsp+0D8h+var_48], rax
0x140063e7f  test    rax, rax
0x140063e82  jnz     short loc_140063E9A
0x140063e84  mov     esi, 0C01A000Dh
0x140063e89  mov     [rsp+0D8h+var_98], esi
0x140063e8d  mov     rbx, [rsp+0D8h+arg_0]
0x140063e95  jmp     loc_14006434F
0x140063e9a  mov     dword ptr [r14], 0
0x140063ea1  test    [rsp+0D8h+arg_30], 2
0x140063ea9  jz      loc_140064143
0x140063eaf  mov     edi, 1FEh
0x140063eb4  cmp     r12d, r15d
0x140063eb7  jnb     loc_140064119
0x140063ebd  mov     eax, [r14]
0x140063ec0  cmp     eax, dword ptr [rsp+0D8h+arg_48]
0x140063ec7  jnb     loc_140064119
0x140063ecd  cmp     r12d, 400h
0x140063ed4  jnb     loc_140064119
0x140063eda  add     eax, [rsp+0D8h+arg_28]
0x140063ee1  and     eax, 3FFh
0x140063ee6  mov     rcx, [rsp+0D8h+arg_8]
0x140063eee  mov     r13d, [rcx+rax*4]
0x140063ef2  cmp     r13d, 0FFFFFFFFh
0x140063ef6  jz      loc_140064119
0x140063efc  mov     eax, r13d
0x140063eff  mov     edx, [rdx+r13*4+328h]; int
0x140063f07  test    edx, edx
0x140063f09  jz      loc_1400640FC
0x140063f0f  lea     r9, [rsp+0D8h+var_58]; struct _CLFS_CONTAINER_CONTEXT **
0x140063f17  mov     r8d, r13d; unsigned int
0x140063f1a  mov     rbx, [rsp+0D8h+arg_0]
0x140063f22  mov     rcx, rbx; this
0x140063f25  call    ?GetSymbol@CClfsBaseFile@@QEAAJJKPEAPEAU_CLFS_CONTAINER_CONTEXT@@@Z; CClfsBaseFile::GetSymbol(long,ulong,_CLFS_CONTAINER_CONTEXT * *)
0x140063f2a  mov     esi, eax
0x140063f2c  mov     [rsp+0D8h+var_98], eax
0x140063f30  test    eax, eax
0x140063f32  js      loc_14006434A
0x140063f38  mov     r15, [rsp+0D8h+var_58]
0x140063f40  mov     edx, [r15+24h]
0x140063f44  test    dl, 1
0x140063f47  jz      short loc_140063F4E
0x140063f49  jmp     loc_1400640FC
0x140063f4e  mov     eax, [r14]
0x140063f51  lea     rbx, [rax+rax*8]
0x140063f55  shl     rbx, 6
0x140063f59  add     rbx, [rsp+0D8h+arg_38]
0x140063f61  mov     [rbx+230h], edx
0x140063f67  mov     eax, [r15+10h]
0x140063f6b  mov     [rbx+234h], eax
0x140063f71  mov     eax, [r15+14h]
0x140063f75  mov     [rbx+238h], eax
0x140063f7b  mov     eax, [r15+24h]
0x140063f7f  test    al, 38h
0x140063f81  jnz     loc_14006400A
0x140063f87  mov     edi, [r15+14h]
0x140063f8b  mov     rsi, [rsp+0D8h+plsn]
0x140063f93  mov     rcx, rsi; plsn
0x140063f96  call    ClfsLsnContainer
0x140063f9b  cmp     edi, eax
0x140063f9d  jnb     short loc_140063FB0
0x140063f9f  test    rsi, rsi
0x140063fa2  jz      short loc_140063FCD
0x140063fa4  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x140063fab  cmp     rax, [rsi]
0x140063fae  jnz     short loc_140063FCD
0x140063fb0  mov     rcx, [rsp+0D8h+arg_10]; plsn
0x140063fb8  call    ClfsLsnContainer
0x140063fbd  cmp     edi, eax
0x140063fbf  ja      short loc_140063FCD
0x140063fc1  mov     dword ptr [rbx+230h], 4
0x140063fcb  jmp     short loc_140064005
0x140063fcd  mov     rcx, [rsp+0D8h+arg_20]; plsn
0x140063fd5  call    ClfsLsnContainer
0x140063fda  cmp     eax, edi
0x140063fdc  ja      short loc_140063FFB
0x140063fde  mov     rcx, [rsp+0D8h+arg_20]; plsn
0x140063fe6  call    ClfsLsnContainer
0x140063feb  cmp     eax, edi
0x140063fed  jb      short loc_140063FFB
0x140063fef  mov     dword ptr [rbx+230h], 10h
0x140063ff9  jmp     short loc_140064005
0x140063ffb  mov     dword ptr [rbx+230h], 2
0x140064005  mov     edi, 1FEh
0x14006400a  mov     rdx, rbx; struct _CLS_CONTAINER_INFORMATION *
0x14006400d  mov     rcx, [r15+18h]; this
0x140064011  call    ?QueryContainerInfo@CClfsAuthContainer@@QEAAJAEAU_CLS_CONTAINER_INFORMATION@@@Z; CClfsAuthContainer::QueryContainerInfo(_CLS_CONTAINER_INFORMATION &)
0x140064016  lea     r8, [rsp+0D8h+var_68]; struct _UNICODE_STRING *
0x14006401b  mov     edx, r13d; unsigned int
0x14006401e  mov     rcx, [rsp+0D8h+arg_0]; this
0x140064026  call    ?GetContainerName@CClfsBaseFile@@QEAAJKAEAU_UNICODE_STRING@@@Z; CClfsBaseFile::GetContainerName(ulong,_UNICODE_STRING &)
0x14006402b  mov     esi, eax
0x14006402d  mov     [rsp+0D8h+var_98], eax
0x140064031  test    eax, eax
0x140064033  js      loc_140064342
0x140064039  movzx   eax, [rsp+0D8h+var_68.Length]
0x14006403e  mov     [rbx+28h], eax
0x140064041  mov     [rbx+2Ch], edi
0x140064044  movzx   eax, [rsp+0D8h+var_68.Length]
0x140064049  cmp     eax, edi
0x14006404b  jnb     short loc_140064050
0x14006404d  mov     [rbx+2Ch], eax
0x140064050  lea     rax, [rbx+30h]
0x140064054  mov     [rsp+0D8h+var_80.Buffer], rax
0x140064059  xor     eax, eax
0x14006405b  mov     dword ptr [rsp+0D8h+var_80.Length], 1FE0000h
0x140064063  lea     rdx, asc_14001C860; "\\??\\"
0x14006406a  lea     rcx, [rsp+0D8h+DestinationString]; DestinationString
0x14006406f  call    cs:__imp_RtlInitUnicodeString
0x140064076  nop     dword ptr [rax+rax+00h]
0x14006407b  movaps  xmm0, xmmword ptr [rsp+0D8h+var_68.Length]
0x140064080  movdqa  xmmword ptr [rsp+0D8h+String2.Length], xmm0
0x140064086  cmp     [rsp+0D8h+arg_40], 1
0x14006408e  jnz     short loc_1400640DD
0x140064090  xor     r8d, r8d; CaseInSensitive
0x140064093  lea     rdx, [rsp+0D8h+String2]; String2
0x140064098  lea     rcx, [rsp+0D8h+DestinationString]; String1
0x14006409d  call    cs:__imp_RtlPrefixUnicodeString
0x1400640a4  nop     dword ptr [rax+rax+00h]
0x1400640a9  test    al, al
0x1400640ab  jz      short loc_1400640DD
0x1400640ad  movzx   ecx, [rsp+0D8h+DestinationString.Length]
0x1400640b2  shr     rcx, 1
0x1400640b5  mov     rax, [rsp+0D8h+String2.Buffer]
0x1400640ba  lea     rcx, [rax+rcx*2]
0x1400640be  mov     [rsp+0D8h+String2.Buffer], rcx
0x1400640c3  movzx   eax, [rsp+0D8h+DestinationString.Length]
0x1400640c8  sub     [rsp+0D8h+String2.Length], ax
0x1400640cd  sub     [rsp+0D8h+String2.MaximumLength], ax
0x1400640d2  sub     [rbx+2Ch], eax
0x1400640d5  movzx   eax, [rsp+0D8h+DestinationString.Length]
0x1400640da  sub     [rbx+28h], eax
0x1400640dd  lea     rdx, [rsp+0D8h+String2]; SourceString
0x1400640e2  lea     rcx, [rsp+0D8h+var_80]; DestinationString
0x1400640e7  call    cs:__imp_RtlCopyUnicodeString
0x1400640ee  nop     dword ptr [rax+rax+00h]
0x1400640f3  shr     dword ptr [rbx+2Ch], 1
0x1400640f6  shr     dword ptr [rbx+28h], 1
0x1400640f9  inc     dword ptr [r14]
0x1400640fc  inc     r12d
0x1400640ff  mov     [rsp+0D8h+var_50], r12d
0x140064107  mov     rdx, [rsp+0D8h+var_48]
0x14006410f  mov     r15d, [rsp+0D8h+var_70]
0x140064114  jmp     loc_140063EB4
0x140064119  mov     eax, [r14]
0x14006411c  mov     ecx, [rsp+0D8h+arg_28]
0x140064123  add     ecx, eax
0x140064125  mov     rbx, [rsp+0D8h+arg_50]
0x14006412d  mov     [rbx], ecx
0x14006412f  cmp     ecx, 0FFFFFFFFh
0x140064132  jnz     loc_140064342
0x140064138  mov     dword ptr [rbx], 0FFFFFFFEh
0x14006413e  jmp     loc_140064342
0x140064143  mov     edi, [rsp+0D8h+arg_28]
0x14006414a  cmp     r12d, r15d
0x14006414d  jnb     loc_14006432A
0x140064153  mov     ecx, [r14]
0x140064156  cmp     ecx, dword ptr [rsp+0D8h+arg_48]
0x14006415d  jnb     loc_14006432A
0x140064163  cmp     r12d, 400h
0x14006416a  jnb     loc_14006432A
0x140064170  mov     eax, edi
0x140064172  sub     eax, ecx
0x140064174  js      loc_14006432A
0x14006417a  and     eax, 3FFh
0x14006417f  mov     rcx, [rsp+0D8h+arg_8]
0x140064187  mov     r15d, [rcx+rax*4]
0x14006418b  cmp     r15d, 0FFFFFFFFh
0x14006418f  jz      loc_14006432A
0x140064195  mov     eax, r15d
0x140064198  mov     edx, [rdx+r15*4+328h]; int
0x1400641a0  test    edx, edx
0x1400641a2  jz      loc_14006430D
0x1400641a8  lea     r9, [rsp+0D8h+var_58]; struct _CLFS_CONTAINER_CONTEXT **
0x1400641b0  mov     r8d, r15d; unsigned int
0x1400641b3  mov     rcx, r13; this
0x1400641b6  call    ?GetSymbol@CClfsBaseFile@@QEAAJJKPEAPEAU_CLFS_CONTAINER_CONTEXT@@@Z; CClfsBaseFile::GetSymbol(long,ulong,_CLFS_CONTAINER_CONTEXT * *)
0x1400641bb  mov     esi, eax
0x1400641bd  mov     [rsp+0D8h+var_98], eax
0x1400641c1  mov     rcx, [rsp+0D8h+var_58]
0x1400641c9  test    rcx, rcx
0x1400641cc  jz      loc_140064342
0x1400641d2  mov     edx, [rcx+24h]
0x1400641d5  test    dl, 1
0x1400641d8  jz      short loc_1400641DF
0x1400641da  jmp     loc_14006430D
0x1400641df  mov     eax, [r14]
0x1400641e2  lea     rbx, [rax+rax*8]
0x1400641e6  shl     rbx, 6
0x1400641ea  add     rbx, [rsp+0D8h+arg_38]
0x1400641f2  mov     [rbx+230h], edx
0x1400641f8  mov     eax, [rcx+10h]
0x1400641fb  mov     [rbx+234h], eax
0x140064201  mov     eax, [rcx+14h]
0x140064204  mov     [rbx+238h], eax
0x14006420a  mov     rdx, rbx; struct _CLS_CONTAINER_INFORMATION *
0x14006420d  mov     rcx, [rcx+18h]; this
0x140064211  call    ?QueryContainerInfo@CClfsAuthContainer@@QEAAJAEAU_CLS_CONTAINER_INFORMATION@@@Z; CClfsAuthContainer::QueryContainerInfo(_CLS_CONTAINER_INFORMATION &)
0x140064216  lea     r8, [rsp+0D8h+var_68]; struct _UNICODE_STRING *
0x14006421b  mov     edx, r15d; unsigned int
0x14006421e  mov     rcx, r13; this
0x140064221  call    ?GetContainerName@CClfsBaseFile@@QEAAJKAEAU_UNICODE_STRING@@@Z; CClfsBaseFile::GetContainerName(ulong,_UNICODE_STRING &)
0x140064226  mov     esi, eax
0x140064228  mov     [rsp+0D8h+var_98], eax
0x14006422c  test    eax, eax
0x14006422e  js      loc_140064342
0x140064234  movzx   eax, [rsp+0D8h+var_68.Length]
0x140064239  mov     [rbx+28h], eax
0x14006423c  mov     ecx, 1FEh
0x140064241  mov     [rbx+2Ch], ecx
0x140064244  movzx   eax, [rsp+0D8h+var_68.Length]
0x140064249  cmp     eax, ecx
0x14006424b  jnb     short loc_140064250
0x14006424d  mov     [rbx+2Ch], eax
0x140064250  lea     rax, [rbx+30h]
0x140064254  mov     [rsp+0D8h+var_80.Buffer], rax
0x140064259  mov     dword ptr [rsp+0D8h+var_80.Length], 1FE0000h
0x140064261  lea     rdx, asc_14001C860; "\\??\\"
0x140064268  lea     rcx, [rsp+0D8h+DestinationString]; DestinationString
0x14006426d  call    cs:__imp_RtlInitUnicodeString
0x140064274  nop     dword ptr [rax+rax+00h]
0x140064279  movaps  xmm0, xmmword ptr [rsp+0D8h+var_68.Length]
0x14006427e  movdqa  xmmword ptr [rsp+0D8h+String2.Length], xmm0
0x140064284  cmp     [rsp+0D8h+arg_40], 1
0x14006428c  jnz     short loc_1400642DB
0x14006428e  xor     r8d, r8d; CaseInSensitive
0x140064291  lea     rdx, [rsp+0D8h+String2]; String2
0x140064296  lea     rcx, [rsp+0D8h+DestinationString]; String1
0x14006429b  call    cs:__imp_RtlPrefixUnicodeString
0x1400642a2  nop     dword ptr [rax+rax+00h]
0x1400642a7  test    al, al
0x1400642a9  jz      short loc_1400642DB
0x1400642ab  movzx   ecx, [rsp+0D8h+DestinationString.Length]
0x1400642b0  shr     rcx, 1
0x1400642b3  mov     rax, [rsp+0D8h+String2.Buffer]
0x1400642b8  lea     rcx, [rax+rcx*2]
0x1400642bc  mov     [rsp+0D8h+String2.Buffer], rcx
0x1400642c1  movzx   eax, [rsp+0D8h+DestinationString.Length]
0x1400642c6  sub     [rsp+0D8h+String2.Length], ax
0x1400642cb  sub     [rsp+0D8h+String2.MaximumLength], ax
0x1400642d0  sub     [rbx+2Ch], eax
0x1400642d3  movzx   eax, [rsp+0D8h+DestinationString.Length]
0x1400642d8  sub     [rbx+28h], eax
0x1400642db  lea     rdx, [rsp+0D8h+String2]; SourceString
0x1400642e0  lea     rcx, [rsp+0D8h+var_80]; DestinationString
0x1400642e5  call    cs:__imp_RtlCopyUnicodeString
0x1400642ec  nop     dword ptr [rax+rax+00h]
0x1400642f1  movzx   edx, [rsp+0D8h+var_80.Length]
0x1400642f6  shr     rdx, 1
0x1400642f9  xor     ecx, ecx
0x1400642fb  mov     rax, [rsp+0D8h+var_80.Buffer]
0x140064300  mov     [rax+rdx*2], cx
0x140064304  shr     dword ptr [rbx+2Ch], 1
0x140064307  shr     dword ptr [rbx+28h], 1
0x14006430a  inc     dword ptr [r14]
0x14006430d  inc     r12d
  ... truncated ...
```
