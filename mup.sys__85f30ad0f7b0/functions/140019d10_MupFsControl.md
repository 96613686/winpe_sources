# MupFsControl

- ea: `0x140019d10`
- end: `0x140019f3e`
- name: `MupFsControl`
- size: `558`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x140001070`
- `0x140001c10`
- `0x140010534`
- `0x14001067c`
- `0x1400123a4`
- `0x140012750`
- `0x140013f38`
- `0x140014cc0`
- `0x140014d38`
- `0x140019994`
- `0x140019d10`
- `0x14001bae0`
- `0x14001bb80`
- `0x14001bbb0`
- `0x14001dacc`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140019df7`
- `ntoskrnl!IofCompleteRequest` at `0x140019df7`

## pseudocode

```c
__int64 __fastcall MupFsControl(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  unsigned int LowPart; // eax
  PFILE_OBJECT FileObject; // rdx
  ULONG_PTR FileContext; // rbp
  struct _IO_STACK_LOCATION *v7; // rcx
  __int64 SiloFromFileObject; // rax
  unsigned int ContainerContextFromSilo; // edi
  unsigned int UncCacheInfo; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int Options; // ebp
  __int64 v15; // rax
  __int64 UncCachePrefixTable; // rax
  __int64 v17; // r9
  struct _IRP *MasterIrp; // rax
  _WORD v19[2]; // [rsp+30h] [rbp-28h] BYREF
  int v20; // [rsp+34h] [rbp-24h]
  struct _IRP *v21; // [rsp+38h] [rbp-20h]
  __int64 v22; // [rsp+68h] [rbp+10h] BYREF
  PVOID P; // [rsp+70h] [rbp+18h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  if ( LowPart == 1048620 )
  {
    a2->IoStatus.Information = 0;
    UncCacheInfo = MupFsctlGetUncCacheInfo(a2);
  }
  else
  {
    FileObject = CurrentStackLocation->FileObject;
    if ( LowPart <= 0x100038 )
    {
      if ( LowPart == 1048632 )
      {
        a2->IoStatus.Information = 0;
        UncCacheInfo = MupFsctlGetUncHardeningPrefixTable(a2, FileObject);
      }
      else
      {
        v12 = LowPart - 1048580;
        if ( !v12 )
        {
          if ( a2->RequestorMode )
            ContainerContextFromSilo = -1073741790;
          else
            ContainerContextFromSilo = MupRegisterUncProvider(a2, FileObject);
LABEL_20:
          a2->IoStatus.Status = ContainerContextFromSilo;
          goto LABEL_11;
        }
        v13 = v12 - 44;
        if ( v13 )
        {
          if ( v13 != 4 )
          {
LABEL_5:
            FileContext = MupFindFileContext(CurrentStackLocation->FileObject);
            if ( !FileContext )
            {
              ContainerContextFromSilo = -1073741808;
              a2->IoStatus.Status = -1073741808;
              goto LABEL_11;
            }
            v7 = a2->Tail.Overlay.CurrentStackLocation;
            v22 = 0;
            P = 0;
            SiloFromFileObject = MupGetSiloFromFileObject(v7->FileObject);
            ContainerContextFromSilo = MupGetContainerContextFromSilo(SiloFromFileObject, &v22);
            if ( !ContainerContextFromSilo )
            {
              ContainerContextFromSilo = MupCreateIrpContext(FileContext, (__int64)&P);
              if ( !ContainerContextFromSilo )
                return MupStateMachine(P);
            }
            goto LABEL_20;
          }
          a2->IoStatus.Information = 0;
          UncCacheInfo = MupFsctlGetSurrogateProviderList(a2, FileObject);
        }
        else
        {
          a2->IoStatus.Information = 0;
          UncCacheInfo = MupFsctlGetUncProviderList(a2, FileObject);
        }
      }
    }
    else
    {
      if ( LowPart != 1048636 )
      {
        if ( LowPart == 1081384 )
        {
          Options = CurrentStackLocation->Parameters.Create.Options;
          v22 = 0;
          ContainerContextFromSilo = -1073741811;
          if ( (Options & 1) == 0 && Options < 0xFFFF )
          {
            v15 = MupGetSiloFromFileObject(FileObject);
            ContainerContextFromSilo = MupGetContainerContextFromSilo(v15, &v22);
            if ( !ContainerContextFromSilo )
            {
              UncCachePrefixTable = MupGetUncCachePrefixTable(v22);
              v17 = UncCachePrefixTable;
              if ( Options == 2 && a2->AssociatedIrp.MasterIrp->Type == 42 )
              {
                MupFlushKnownPrefixTable(UncCachePrefixTable, 0, 0, UncCachePrefixTable);
              }
              else
              {
                MasterIrp = a2->AssociatedIrp.MasterIrp;
                v20 = 0;
                v21 = MasterIrp;
                v19[0] = Options;
                v19[1] = Options;
                if ( !(unsigned __int8)MupFlushPrefixEntry(v17, v19) )
                  ContainerContextFromSilo = -1073741275;
              }
            }
          }
          a2->IoStatus.Information = 0;
          a2->IoStatus.Status = ContainerContextFromSilo;
          goto LABEL_11;
        }
        goto LABEL_5;
      }
      a2->IoStatus.Information = 0;
      UncCacheInfo = MupFsctlQueryUncHardeningConfigurationForPath(a2, FileObject);
    }
  }
  ContainerContextFromSilo = UncCacheInfo;
  a2->IoStatus.Status = UncCacheInfo;
LABEL_11:
  IofCompleteRequest(a2, 2);
  return ContainerContextFromSilo;
}

```

## disassembly

```asm
0x140019d10  mov     [rsp+arg_0], rbx
0x140019d15  push    rbp
0x140019d16  push    rsi
0x140019d17  push    rdi
0x140019d18  sub     rsp, 40h
0x140019d1c  mov     rcx, [rdx+0B8h]
0x140019d23  mov     rbx, rdx
0x140019d26  mov     eax, [rcx+18h]
0x140019d29  cmp     eax, 10002Ch
0x140019d2e  jz      loc_140019DDF
0x140019d34  mov     rdx, [rcx+30h]
0x140019d38  cmp     eax, 100038h
0x140019d3d  jbe     loc_140019E13
0x140019d43  cmp     eax, 10003Ch
0x140019d48  jz      loc_140019F2B
0x140019d4e  cmp     eax, 108028h
0x140019d53  jz      loc_140019E86
0x140019d59  mov     rcx, rdx
0x140019d5c  call    MupFindFileContext
0x140019d61  mov     rbp, rax
0x140019d64  test    rax, rax
0x140019d67  jz      loc_140019E79
0x140019d6d  mov     rcx, [rbx+0B8h]
0x140019d74  xor     esi, esi
0x140019d76  mov     [rsp+58h+arg_8], rsi
0x140019d7b  mov     [rsp+58h+P], rsi
0x140019d80  mov     rcx, [rcx+30h]
0x140019d84  call    MupGetSiloFromFileObject
0x140019d89  mov     rcx, rax
0x140019d8c  lea     rdx, [rsp+58h+arg_8]
0x140019d91  call    MupGetContainerContextFromSilo
0x140019d96  mov     edi, eax
0x140019d98  test    eax, eax
0x140019d9a  jnz     loc_140019E55
0x140019da0  mov     rdx, [rsp+58h+arg_8]
0x140019da5  lea     rax, [rsp+58h+P]
0x140019daa  xor     r9d, r9d
0x140019dad  mov     [rsp+58h+var_38], rax; __int64
0x140019db2  mov     r8, rbx
0x140019db5  mov     rcx, rbp; BugCheckParameter4
0x140019db8  call    MupCreateIrpContext
0x140019dbd  mov     edi, eax
0x140019dbf  test    eax, eax
0x140019dc1  jnz     loc_140019E55
0x140019dc7  mov     rcx, [rsp+58h+P]; P
0x140019dcc  call    MupStateMachine
0x140019dd1  mov     rbx, [rsp+58h+arg_0]
0x140019dd6  add     rsp, 40h
0x140019dda  pop     rdi
0x140019ddb  pop     rsi
0x140019ddc  pop     rbp
0x140019ddd  retn
0x140019ddf  xor     esi, esi
0x140019de1  mov     rcx, rbx
0x140019de4  mov     [rdx+38h], rsi
0x140019de8  call    MupFsctlGetUncCacheInfo
0x140019ded  mov     edi, eax
0x140019def  mov     [rbx+30h], eax
0x140019df2  mov     dl, 2; PriorityBoost
0x140019df4  mov     rcx, rbx; Irp
0x140019df7  call    cs:__imp_IofCompleteRequest
0x140019dfe  nop     dword ptr [rax+rax+00h]
0x140019e03  mov     rbx, [rsp+58h+arg_0]
0x140019e08  mov     eax, edi
0x140019e0a  add     rsp, 40h
0x140019e0e  pop     rdi
0x140019e0f  pop     rsi
0x140019e10  pop     rbp
0x140019e11  retn
0x140019e13  jz      short loc_140019E66
0x140019e15  sub     eax, 100004h
0x140019e1a  jz      short loc_140019E4A
0x140019e1c  sub     eax, 2Ch ; ','
0x140019e1f  jz      short loc_140019E3A
0x140019e21  cmp     eax, 4
0x140019e24  jnz     loc_140019D59
0x140019e2a  xor     esi, esi
0x140019e2c  mov     rcx, rbx
0x140019e2f  mov     [rbx+38h], rsi
0x140019e33  call    MupFsctlGetSurrogateProviderList
0x140019e38  jmp     short loc_140019DED
0x140019e3a  xor     esi, esi
0x140019e3c  mov     rcx, rbx
0x140019e3f  mov     [rbx+38h], rsi
0x140019e43  call    MupFsctlGetUncProviderList
0x140019e48  jmp     short loc_140019DED
0x140019e4a  cmp     byte ptr [rbx+40h], 0
0x140019e4e  jz      short loc_140019E5A
0x140019e50  mov     edi, 0C0000022h
0x140019e55  mov     [rbx+30h], edi
0x140019e58  jmp     short loc_140019DF2
0x140019e5a  mov     rcx, rbx
0x140019e5d  call    MupRegisterUncProvider
0x140019e62  mov     edi, eax
0x140019e64  jmp     short loc_140019E55
0x140019e66  xor     esi, esi
0x140019e68  mov     rcx, rbx
0x140019e6b  mov     [rbx+38h], rsi
0x140019e6f  call    MupFsctlGetUncHardeningPrefixTable
0x140019e74  jmp     loc_140019DED
0x140019e79  mov     edi, 0C0000010h
0x140019e7e  mov     [rbx+30h], edi
0x140019e81  jmp     loc_140019DF2
0x140019e86  mov     ebp, [rcx+10h]
0x140019e89  xor     esi, esi
0x140019e8b  mov     [rsp+58h+arg_8], rsi
0x140019e90  mov     edi, 0C000000Dh
0x140019e95  test    bpl, 1
0x140019e99  jnz     loc_140019F1F
0x140019e9f  cmp     ebp, 0FFFFh
0x140019ea5  jnb     short loc_140019F1F
0x140019ea7  mov     rcx, rdx
0x140019eaa  call    MupGetSiloFromFileObject
0x140019eaf  mov     rcx, rax
0x140019eb2  lea     rdx, [rsp+58h+arg_8]
0x140019eb7  call    MupGetContainerContextFromSilo
0x140019ebc  mov     edi, eax
0x140019ebe  test    eax, eax
0x140019ec0  jnz     short loc_140019F1F
0x140019ec2  mov     rcx, [rsp+58h+arg_8]
0x140019ec7  call    MupGetUncCachePrefixTable
0x140019ecc  mov     r9, rax
0x140019ecf  cmp     ebp, 2
0x140019ed2  jnz     short loc_140019EED
0x140019ed4  mov     rcx, [rbx+18h]
0x140019ed8  cmp     word ptr [rcx], 2Ah ; '*'
0x140019edc  jnz     short loc_140019EED
0x140019ede  xor     r8d, r8d
0x140019ee1  xor     edx, edx
0x140019ee3  mov     rcx, rax
0x140019ee6  call    MupFlushKnownPrefixTable
0x140019eeb  jmp     short loc_140019F1F
0x140019eed  mov     rax, [rbx+18h]
0x140019ef1  lea     rdx, [rsp+58h+var_28]
0x140019ef6  xorps   xmm0, xmm0
0x140019ef9  mov     rcx, r9
0x140019efc  movups  [rsp+58h+var_28], xmm0
0x140019f01  mov     qword ptr [rsp+58h+var_28+8], rax
0x140019f06  mov     word ptr [rsp+58h+var_28], bp
0x140019f0b  mov     word ptr [rsp+58h+var_28+2], bp
0x140019f10  call    MupFlushPrefixEntry
0x140019f15  test    al, al
0x140019f17  mov     ecx, 0C0000225h
0x140019f1c  cmovz   edi, ecx
0x140019f1f  mov     [rbx+38h], rsi
0x140019f23  mov     [rbx+30h], edi
0x140019f26  jmp     loc_140019DF2
0x140019f2b  xor     esi, esi
0x140019f2d  mov     rcx, rbx
0x140019f30  mov     [rbx+38h], rsi
0x140019f34  call    MupFsctlQueryUncHardeningConfigurationForPath
0x140019f39  jmp     loc_140019DED
```
