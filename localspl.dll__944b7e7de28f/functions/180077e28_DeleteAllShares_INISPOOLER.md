# DeleteAllShares(_INISPOOLER *)

- ea: `0x180077e28`
- end: `0x1800780a5`
- name: `?DeleteAllShares@@YAXPEAU_INISPOOLER@@@Z`
- size: `637`
- prototype: `void __fastcall(struct _INISPOOLER *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18007e088`

## callees

- `0x18003e984`
- `0x18003ea2c`
- `0x18004486c`
- `0x1800547e0`
- `0x180077e28`
- `0x1800c7370`

## import_xrefs

- `srvcli!NetShareDel` at `0x180077f04`
- `srvcli!NetShareDel` at `0x18007800e`
- `srvcli!NetShareDel` at `0x180077f04`
- `srvcli!NetShareDel` at `0x18007800e`
- `srvcli!NetShareEnum` at `0x180077ecb`
- `srvcli!NetShareEnum` at `0x180077fd5`
- `srvcli!NetShareEnum` at `0x180077ecb`
- `srvcli!NetShareEnum` at `0x180077fd5`
- `srvcli!NetShareDelSticky` at `0x180077f2c`
- `srvcli!NetShareDelSticky` at `0x180078036`
- `srvcli!NetShareDelSticky` at `0x180077f2c`
- `srvcli!NetShareDelSticky` at `0x180078036`
- `netutils!NetApiBufferFree` at `0x180077f6c`
- `netutils!NetApiBufferFree` at `0x180078076`
- `netutils!NetApiBufferFree` at `0x180077f6c`
- `netutils!NetApiBufferFree` at `0x180078076`

## string_xrefs

- `0x180077f1c`: `Deleted share %ws using NetShareDel`
- `0x180078026`: `Deleted share %ws using NetShareDel`
- `0x180077f41`: `Deleted share %ws using NetShareDelNetShareDelSticky`
- `0x18007804b`: `Deleted share %ws using NetShareDelNetShareDelSticky`
- `0x180077f15`: `DeleteAllShares`
- `0x180077f36`: `DeleteAllShares`
- `0x18007801f`: `DeleteAllShares`
- `0x180078040`: `DeleteAllShares`
- `0x180077f52`: `Failed to delete share %ws using NetShareDelSticky. Error %d`
- `0x18007805c`: `Failed to delete share %ws using NetShareDelSticky. Error %d`

## pseudocode

```c

```
