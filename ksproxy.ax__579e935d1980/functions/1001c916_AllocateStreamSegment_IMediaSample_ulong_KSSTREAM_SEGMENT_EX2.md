# AllocateStreamSegment(IMediaSample *,ulong,_KSSTREAM_SEGMENT_EX2 * *)

- ea: `0x1001c916`
- end: `0x1001ca56`
- name: `?AllocateStreamSegment@@YGJPAUIMediaSample@@KPAPAU_KSSTREAM_SEGMENT_EX2@@@Z`
- size: `320`
- prototype: `int __stdcall(struct IMediaSample *, unsigned int, struct _KSSTREAM_SEGMENT_EX2 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1001d103`
- `0x1001d9fe`

## callees

- `0x1001c916`
- `0x10033b0a`
- `0x1003a6f2`
- `0x1003a6fd`
- `0x1003a72c`
- `0x1003af9d`
- `0x1003b5e4`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x1001c969`
- `KERNEL32!CreateEventW` at `0x1001c969`
- `KERNEL32!CloseHandle` at `0x1001c9d1`
- `KERNEL32!CloseHandle` at `0x1001c9d1`

## pseudocode

```c
int __userpurge AllocateStreamSegment@<eax>(
        HRESULT (__stdcall *a1)(IMediaSample *this, int)@<edx>,
        int (__stdcall *a2)(IMediaSample *this)@<ecx>,
        struct IMediaSample *a3,
        unsigned int a4,
        struct _KSSTREAM_SEGMENT_EX2 **a5)
{
  IMediaSample_vtbl *v6; // esi
  int SampleProperties; // ebx
  unsigned int v8; // ebx
  _DWORD *v9; // edi
  struct IMediaSample *v11; // [esp+0h] [ebp-54h]
  struct tagAM_SAMPLE2_PROPERTIES *v12; // [esp+4h] [ebp-50h]
  int v13; // [esp+14h] [ebp-40h]
  int v14; // [esp+18h] [ebp-3Ch]
  __int64 v15; // [esp+20h] [ebp-34h]
  __int64 v16; // [esp+28h] [ebp-2Ch]
  int v17; // [esp+38h] [ebp-1Ch]
  int v18; // [esp+3Ch] [ebp-18h]
  HRESULT (__stdcall *hObject)(IMediaSample *, __int64 *, __int64 *); // [esp+48h] [ebp-Ch]

  v6 = (IMediaSample_vtbl *)operator new(0x138u);
  if ( !v6 )
    return -2147024882;
  v8 = (unsigned int)a1 + 48;
  v9 = operator new[](v8);
  if ( !v9 )
  {
    operator delete(v6, 0x138u);
    return -2147024882;
  }
  hObject = (HRESULT (__stdcall *)(IMediaSample *, __int64 *, __int64 *))CreateEventW(0, 0, 0, 0);
  if ( hObject )
  {
    memset(v6, 0, 0x138u);
    memset(v9, 0, v8);
    SampleProperties = GetSampleProperties(v11, v12);
    if ( SampleProperties >= 0 )
    {
      *v9 = (char *)a1 + 48;
      v9[11] = v14;
      v9[1] = v13;
      *((_QWORD *)v9 + 1) = v15;
      v9[4] = 1;
      v9[5] = 1;
      *((_QWORD *)v9 + 3) = v16 - v15;
      v9[10] = v17;
      v9[8] = v18;
      v6->GetSize = a2;
      v6[3].SetMediaTime = hObject;
      v6->GetPointer = (HRESULT (__stdcall *)(IMediaSample *, unsigned __int8 **))hObject;
      v6[3].GetMediaType = (HRESULT (__stdcall *)(IMediaSample *, _AMMediaType **))v9;
      v6[3].SetActualDataLength = a1;
      v6[3].GetActualDataLength = 0;
      a3->__vftable = v6;
    }
    else
    {
      operator delete(v6, 0x138u);
      operator delete[](v9);
      CloseHandle(hObject);
    }
  }
  else
  {
    operator delete(v6, 0x138u);
    operator delete[](v9);
    return -2147467259;
  }
  return SampleProperties;
}

```

## disassembly

```asm
0x1001c916  mov     edi, edi
0x1001c918  push    ebp
0x1001c919  mov     ebp, esp
0x1001c91b  sub     esp, 48h
0x1001c91e  push    ebx
0x1001c91f  push    esi; struct tagAM_SAMPLE2_PROPERTIES *
0x1001c920  push    edi; struct IMediaSample *
0x1001c921  mov     ebx, edx
0x1001c923  mov     [ebp+var_8], ecx
0x1001c926  push    138h; Size
0x1001c92b  mov     [ebp+var_10], ebx
0x1001c92e  call    ??2@YAPAXI@Z; operator new(uint)
0x1001c933  mov     esi, eax
0x1001c935  pop     ecx
0x1001c936  test    esi, esi
0x1001c938  jnz     short loc_1001C944
0x1001c93a  mov     ebx, 8007000Eh
0x1001c93f  jmp     loc_1001CA4D
0x1001c944  add     ebx, 30h ; '0'
0x1001c947  push    ebx; unsigned int
0x1001c948  call    ??_U@YAPAXI@Z; operator new[](uint)
0x1001c94d  mov     edi, eax
0x1001c94f  pop     ecx
0x1001c950  test    edi, edi
0x1001c952  jnz     short loc_1001C963
0x1001c954  push    138h; unsigned int
0x1001c959  push    esi; Block
0x1001c95a  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1001c95f  pop     ecx
0x1001c960  pop     ecx
0x1001c961  jmp     short loc_1001C93A
0x1001c963  xor     eax, eax
0x1001c965  push    eax; lpName
0x1001c966  push    eax; bInitialState
0x1001c967  push    eax; bManualReset
0x1001c968  push    eax; lpEventAttributes
0x1001c969  call    ds:__imp__CreateEventW@16; CreateEventW(x,x,x,x)
0x1001c96f  mov     [ebp+hObject], eax
0x1001c972  push    138h; unsigned int
0x1001c977  test    eax, eax
0x1001c979  jnz     short loc_1001C994
0x1001c97b  push    esi; Block
0x1001c97c  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1001c981  push    edi; Block
0x1001c982  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001c987  add     esp, 0Ch
0x1001c98a  mov     ebx, 80004005h
0x1001c98f  jmp     loc_1001CA4D
0x1001c994  push    0; Val
0x1001c996  push    esi; void *
0x1001c997  call    _memset
0x1001c99c  push    ebx; Size
0x1001c99d  push    0; Val
0x1001c99f  push    edi; void *
0x1001c9a0  call    _memset
0x1001c9a5  mov     ecx, [ebp+var_8]
0x1001c9a8  lea     edx, [ebp+var_44]
0x1001c9ab  add     esp, 18h
0x1001c9ae  call    ?GetSampleProperties@@YGJPAUIMediaSample@@PAUtagAM_SAMPLE2_PROPERTIES@@@Z; GetSampleProperties(IMediaSample *,tagAM_SAMPLE2_PROPERTIES *)
0x1001c9b3  mov     ebx, eax
0x1001c9b5  test    ebx, ebx
0x1001c9b7  jns     short loc_1001C9D9
0x1001c9b9  push    138h; unsigned int
0x1001c9be  push    esi; Block
0x1001c9bf  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1001c9c4  push    edi; Block
0x1001c9c5  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001c9ca  mov     eax, [ebp+hObject]
0x1001c9cd  add     esp, 0Ch
0x1001c9d0  push    eax; hObject
0x1001c9d1  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1001c9d7  jmp     short loc_1001CA4D
0x1001c9d9  mov     edx, [ebp+var_10]
0x1001c9dc  lea     eax, [edx+30h]
0x1001c9df  mov     [edi], eax
0x1001c9e1  mov     eax, [ebp+var_3C]
0x1001c9e4  mov     [edi+2Ch], eax
0x1001c9e7  mov     eax, [ebp+var_40]
0x1001c9ea  mov     [edi+4], eax
0x1001c9ed  mov     eax, dword ptr [ebp+var_34]
0x1001c9f0  mov     ecx, dword ptr [ebp+var_34+4]
0x1001c9f3  mov     [edi+8], eax
0x1001c9f6  xor     eax, eax
0x1001c9f8  mov     [edi+0Ch], ecx
0x1001c9fb  inc     eax
0x1001c9fc  mov     [edi+10h], eax
0x1001c9ff  mov     [edi+14h], eax
0x1001ca02  mov     ecx, dword ptr [ebp+var_2C]
0x1001ca05  sub     ecx, dword ptr [ebp+var_34]
0x1001ca08  mov     eax, dword ptr [ebp+var_2C+4]
0x1001ca0b  sbb     eax, dword ptr [ebp+var_34+4]
0x1001ca0e  mov     [edi+1Ch], eax
0x1001ca11  mov     [edi+18h], ecx
0x1001ca14  mov     eax, [ebp+var_1C]
0x1001ca17  mov     [edi+28h], eax
0x1001ca1a  mov     eax, [ebp+var_18]
0x1001ca1d  mov     [edi+20h], eax
0x1001ca20  mov     eax, [ebp+var_8]
0x1001ca23  mov     [esi+10h], eax
0x1001ca26  mov     eax, [ebp+hObject]
0x1001ca29  mov     [esi+12Ch], eax
0x1001ca2f  mov     [esi+0Ch], eax
0x1001ca32  mov     eax, [ebp+arg_0]
0x1001ca35  mov     [esi+118h], edi
0x1001ca3b  mov     [esi+114h], edx
0x1001ca41  mov     dword ptr [esi+110h], 0
0x1001ca4b  mov     [eax], esi
0x1001ca4d  pop     edi
0x1001ca4e  pop     esi
0x1001ca4f  mov     eax, ebx
0x1001ca51  pop     ebx
0x1001ca52  leave
0x1001ca53  retn    4
```
