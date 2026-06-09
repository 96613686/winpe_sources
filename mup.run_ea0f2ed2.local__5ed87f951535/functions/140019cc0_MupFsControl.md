# MupFsControl

- ea: `0x140019cc0`
- end: `0x140019eee`
- name: `MupFsControl`
- size: `558`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x140001070`
- `0x140001c10`
- `0x140010534`
- `0x14001067c`
- `0x140012354`
- `0x140012700`
- `0x140013ee8`
- `0x140014c70`
- `0x140014ce8`
- `0x140019944`
- `0x140019cc0`
- `0x14001ba90`
- `0x14001bb30`
- `0x14001bb60`
- `0x14001da7c`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140019da7`
- `ntoskrnl!IofCompleteRequest` at `0x140019da7`

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
              ContainerContextFromSilo = MupCreateIrpContext(FileContext, v22, (ULONG_PTR)a2, 0, (__int64 **)&P);
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
                MupFlushKnownPrefixTable(UncCachePrefixTable, 0, 0);
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
0x140019cc0  mov     [rsp+arg_0], rbx
0x140019cc5  push    rbp
0x140019cc6  push    rsi
0x140019cc7  push    rdi
0x140019cc8  sub     rsp, 40h
0x140019ccc  mov     rcx, [rdx+0B8h]
0x140019cd3  mov     rbx, rdx
0x140019cd6  mov     eax, [rcx+18h]
0x140019cd9  cmp     eax, 10002Ch
0x140019cde  jz      loc_140019D8F
0x140019ce4  mov     rdx, [rcx+30h]
0x140019ce8  cmp     eax, 100038h
0x140019ced  jbe     loc_140019DC3
0x140019cf3  cmp     eax, 10003Ch
0x140019cf8  jz      loc_140019EDB
0x140019cfe  cmp     eax, 108028h
0x140019d03  jz      loc_140019E36
0x140019d09  mov     rcx, rdx
0x140019d0c  call    MupFindFileContext
0x140019d11  mov     rbp, rax
0x140019d14  test    rax, rax
0x140019d17  jz      loc_140019E29
0x140019d1d  mov     rcx, [rbx+0B8h]
0x140019d24  xor     esi, esi
0x140019d26  mov     [rsp+58h+arg_8], rsi
0x140019d2b  mov     [rsp+58h+P], rsi
0x140019d30  mov     rcx, [rcx+30h]
0x140019d34  call    MupGetSiloFromFileObject
0x140019d39  mov     rcx, rax
0x140019d3c  lea     rdx, [rsp+58h+arg_8]
0x140019d41  call    MupGetContainerContextFromSilo
0x140019d46  mov     edi, eax
0x140019d48  test    eax, eax
0x140019d4a  jnz     loc_140019E05
0x140019d50  mov     rdx, [rsp+58h+arg_8]
0x140019d55  lea     rax, [rsp+58h+P]
0x140019d5a  xor     r9d, r9d
0x140019d5d  mov     [rsp+58h+var_38], rax; __int64
0x140019d62  mov     r8, rbx
0x140019d65  mov     rcx, rbp; BugCheckParameter4
0x140019d68  call    MupCreateIrpContext
0x140019d6d  mov     edi, eax
0x140019d6f  test    eax, eax
0x140019d71  jnz     loc_140019E05
0x140019d77  mov     rcx, [rsp+58h+P]; P
0x140019d7c  call    MupStateMachine
0x140019d81  mov     rbx, [rsp+58h+arg_0]
0x140019d86  add     rsp, 40h
0x140019d8a  pop     rdi
0x140019d8b  pop     rsi
0x140019d8c  pop     rbp
0x140019d8d  retn
0x140019d8f  xor     esi, esi
0x140019d91  mov     rcx, rbx
0x140019d94  mov     [rdx+38h], rsi
0x140019d98  call    MupFsctlGetUncCacheInfo
0x140019d9d  mov     edi, eax
0x140019d9f  mov     [rbx+30h], eax
0x140019da2  mov     dl, 2; PriorityBoost
0x140019da4  mov     rcx, rbx; Irp
0x140019da7  call    cs:__imp_IofCompleteRequest
0x140019dae  nop     dword ptr [rax+rax+00h]
0x140019db3  mov     rbx, [rsp+58h+arg_0]
0x140019db8  mov     eax, edi
0x140019dba  add     rsp, 40h
0x140019dbe  pop     rdi
0x140019dbf  pop     rsi
0x140019dc0  pop     rbp
0x140019dc1  retn
0x140019dc3  jz      short loc_140019E16
0x140019dc5  sub     eax, 100004h
0x140019dca  jz      short loc_140019DFA
0x140019dcc  sub     eax, 2Ch ; ','
0x140019dcf  jz      short loc_140019DEA
0x140019dd1  cmp     eax, 4
0x140019dd4  jnz     loc_140019D09
0x140019dda  xor     esi, esi
0x140019ddc  mov     rcx, rbx
0x140019ddf  mov     [rbx+38h], rsi
0x140019de3  call    MupFsctlGetSurrogateProviderList
0x140019de8  jmp     short loc_140019D9D
0x140019dea  xor     esi, esi
0x140019dec  mov     rcx, rbx
0x140019def  mov     [rbx+38h], rsi
0x140019df3  call    MupFsctlGetUncProviderList
0x140019df8  jmp     short loc_140019D9D
0x140019dfa  cmp     byte ptr [rbx+40h], 0
0x140019dfe  jz      short loc_140019E0A
0x140019e00  mov     edi, 0C0000022h
0x140019e05  mov     [rbx+30h], edi
0x140019e08  jmp     short loc_140019DA2
0x140019e0a  mov     rcx, rbx
0x140019e0d  call    MupRegisterUncProvider
0x140019e12  mov     edi, eax
0x140019e14  jmp     short loc_140019E05
0x140019e16  xor     esi, esi
0x140019e18  mov     rcx, rbx
0x140019e1b  mov     [rbx+38h], rsi
0x140019e1f  call    MupFsctlGetUncHardeningPrefixTable
0x140019e24  jmp     loc_140019D9D
0x140019e29  mov     edi, 0C0000010h
0x140019e2e  mov     [rbx+30h], edi
0x140019e31  jmp     loc_140019DA2
0x140019e36  mov     ebp, [rcx+10h]
0x140019e39  xor     esi, esi
0x140019e3b  mov     [rsp+58h+arg_8], rsi
0x140019e40  mov     edi, 0C000000Dh
0x140019e45  test    bpl, 1
0x140019e49  jnz     loc_140019ECF
0x140019e4f  cmp     ebp, 0FFFFh
0x140019e55  jnb     short loc_140019ECF
0x140019e57  mov     rcx, rdx
0x140019e5a  call    MupGetSiloFromFileObject
0x140019e5f  mov     rcx, rax
0x140019e62  lea     rdx, [rsp+58h+arg_8]
0x140019e67  call    MupGetContainerContextFromSilo
0x140019e6c  mov     edi, eax
0x140019e6e  test    eax, eax
0x140019e70  jnz     short loc_140019ECF
0x140019e72  mov     rcx, [rsp+58h+arg_8]
0x140019e77  call    MupGetUncCachePrefixTable
0x140019e7c  mov     r9, rax
0x140019e7f  cmp     ebp, 2
0x140019e82  jnz     short loc_140019E9D
0x140019e84  mov     rcx, [rbx+18h]
0x140019e88  cmp     word ptr [rcx], 2Ah ; '*'
0x140019e8c  jnz     short loc_140019E9D
0x140019e8e  xor     r8d, r8d
0x140019e91  xor     edx, edx
0x140019e93  mov     rcx, rax
0x140019e96  call    MupFlushKnownPrefixTable
0x140019e9b  jmp     short loc_140019ECF
0x140019e9d  mov     rax, [rbx+18h]
0x140019ea1  lea     rdx, [rsp+58h+var_28]
0x140019ea6  xorps   xmm0, xmm0
0x140019ea9  mov     rcx, r9
0x140019eac  movups  [rsp+58h+var_28], xmm0
0x140019eb1  mov     qword ptr [rsp+58h+var_28+8], rax
0x140019eb6  mov     word ptr [rsp+58h+var_28], bp
0x140019ebb  mov     word ptr [rsp+58h+var_28+2], bp
0x140019ec0  call    MupFlushPrefixEntry
0x140019ec5  test    al, al
0x140019ec7  mov     ecx, 0C0000225h
0x140019ecc  cmovz   edi, ecx
0x140019ecf  mov     [rbx+38h], rsi
0x140019ed3  mov     [rbx+30h], edi
0x140019ed6  jmp     loc_140019DA2
0x140019edb  xor     esi, esi
0x140019edd  mov     rcx, rbx
0x140019ee0  mov     [rbx+38h], rsi
0x140019ee4  call    MupFsctlQueryUncHardeningConfigurationForPath
0x140019ee9  jmp     loc_140019D9D
```
